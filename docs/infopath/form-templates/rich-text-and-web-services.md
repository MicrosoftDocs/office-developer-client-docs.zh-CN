---
title: 格式文本和 Web 服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 53fddc3f-e9d9-db76-6b84-11befdb23fb0
description: Microsoft InfoPath 支持将表单中的格式文本框控件绑定到从 Web 服务收到的 XML 元素，以及通过 Web 服务将数据从格式文本框控件提交到 XML 元素。该元素必须遵循可扩展超文本标记语言 (XHTML) 格式。例如，名为 MyRichTextElement 的元素（包含格式文本）的架构将具有以下 XML 架构定义：
ms.openlocfilehash: d10f4a8cedcff43d1c351068859aee0edf607c81
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299844"
---
# <a name="rich-text-and-web-services"></a>格式文本和 Web 服务

Microsoft InfoPath supports binding a **Rich Text Box** control in a form to an XML element that is received from a Web service, and submitting data from a rich text box control to an XML element through a Web service. The element must adhere to the Extensible HyperText Markup Language (XHTML) format. For example, the schema for an element named  `MyRichTextElement` that contains rich text would have the following XML schema definition: 
  
```XML
<xsd:element name="MyRichTextElement"> 
    <xsd:complexType mixed="true"> 
        <xsd:sequence> 
            <xsd:any namespace="https://www.w3.org/1999/xhtml" processContents="lax" 
                minOccurs="0" maxOccurs="unbounded"/> 
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element>
```

Before a **Rich Text Box** control can be bound with the XHTML element, the element should be wrapped with a wrapper node; this wrapper node can belong to any arbitrary namespace. The wrapper node can look like this: 
  
```xml
<xhtmlNode xmlns="https:// someNamespace"> 
    <div xmlns="https://www.w3.org/1999/xhtml">Your rich text here</div> 
</xhtmlNode>
```

本主题概述了创建可发送和接收 XHTML 的 Web 服务的过程，以及如何使用 InfoPath 来绑定到 Web 服务参数。本主题未提供有关如何创建此类 Web 服务的详细说明，并假定您已经熟悉如何使用 Web 服务。
  
## <a name="how-to-design-a-web-service-to-receive-and-send-xhtml"></a>如何设计 Web 服务来接收和发送 XHTML

示例 Web 服务将其发送和接收的 XHTML 数据存储在服务器上的一个 XML 文件中。名为 out.xml 的此文件充当存储 XHTML 数据的数据源。将公开以下两个 Web 方法，以允许客户端应用程序与 XHTML 数据源协调工作： `getXhtml` 和  `setXhtml`。 `getXhtml` Web 服务方法返回一个 **XmlNode**，其中包含可绑定到 InfoPath 格式文本框控件的 XHTML。 `setXhtml` Web 服务方法接受 **XmlNode** 作为数据以存储在 out.xml 文件中。 
  
> [!NOTE]
> 这些 Web 方法需要对 **System.IO** 和 **System.Xml** 命名空间进行引用的 **using** 语句。 
  
`getXhtml` Web 服务方法会尝试加载要从驱动器 C 上 Data 文件夹中的 out.xml 文件返回的 XML 数据。如果由于找不到文件或文件未包含有效的 XML 而失败，则该方法将返回一个引用 XHTML 命名空间的空 **DIV** HTML 元素。 
  
```cs
[WebMethod]
public XmlNode getXhtml()  
{  
            // This is the returned XmlDocument upon Query from InfoPath 
            XmlDocument document = new XmlDocument(); 
 
            // Create a wrapping node with the name of the rich text field. 
            // The "https://someNameSpace" can be any arbitrary namespace 
            XmlNode richNode = document.CreateNode 
                        (XmlNodeType.Element, "MyRichTextElement", "https://someNameSpace"); 
 
            // Temporary XmlDocument 
            XmlDocument tempDocument = new XmlDocument(); 
            try 
            { 
                // Read the saved rich text data from the local machine 
                tempDocument.Load(@"c:\Data\out.xml"); 
            } 
            catch (XmlException) 
            { 
                // If the file does not exist or content is not valid XML 
                tempDocument.LoadXml("<div xmlns=\"https://www.w3.org/1999/xhtml\"></div>"); 
            } 
 
            // Add the file content to the xml 
            richNode.AppendChild 
                        (document.ImportNode(tempDocument.DocumentElement, true)); 
 
            return richNode; 
}  

```

The  `setXhtml` Web Service method accepts XHTML from a **Rich Text Box** control on an InfoPath form. Because Web services do not support a node list, when a rich text field that contains multiple lines is sent to a Web service, the Web service only accepts the first line and ignores the rest. 
  
The sample  `setXhtml` method assumes that it will receive a top-level XML node, which in most cases will be wrapped in a **DIV** element. If the XML received does not contain a wrapping element, for example when text within the **Rich Text Box** control has no formatting, this method will detect this by checking whether the **NodeType** property indicates that the XML passed in is a text node. If the XML is a text node, the method creates a **DIV** element and copies the text node contents to the **DIV** so that the **DIV** contains a text node child with the text that was sent to the Web service. The XML received by this method is written to the out.xml file in the Data folder on the drive C. 
  
> [!NOTE]
> 编写示例  `setXhtml` 方法的目的是为了接受任何大小的 XHTML 数据。在实际应用中，您应始终检查以确定所提交的数据量，并为可提交的数据量设置一个上限。 
  
```cs
[WebMethod]  
public void setXhtml(XmlNode xn)  
{  
            XmlDocument document = new XmlDocument(); 
 
            if (xn == null) 
            { 
                // If nothing was submitted or the rich text field is empty, 
                // create a DIV that references the XHTML namespace 
                XmlElement div = document.CreateElement("div", "https://www.w3.org/1999/xhtml"); 
                // Copy the node to our own XmlDocument 
                document.AppendChild(div); 
            } 
            if (xn.NodeType == XmlNodeType.Text) 
            { 
                // If plain text is passed in, wrap it in a DIV 
                // that references the XHTML namespace 
                XmlElement div = document.CreateElement("div", "https://www.w3.org/1999/xhtml"); 
                // Copy the text to the DIV. 
                div.AppendChild(document.ImportNode(xn, true)); 
                // Copy the node to our own XmlDocument 
                document.AppendChild(div); 
            } 
            else 
            { 
                // Copy the node to our own XmlDocument 
                document.AppendChild(document.ImportNode(xn, true)); 
            } 
 
            // Save the file to the local machine 
            document.Save(@"c:\Data\out.xml"); 
}  

```

## <a name="how-to-create-an-infopath-form-that-exchanges-data-with-the-sample-web-service"></a>如何创建与示例 Web 服务交换数据的 InfoPath 表单

执行以下步骤以创建一个表单来测试示例 Web 服务。
  
### <a name="to-create-a-form-that-connects-to-the-sample-web-service"></a>创建连接到示例 Web 服务的表单

1. 打开 InfoPath 表单设计器。
    
2. 在“新建”选项卡上，双击“高级表单模板”下的“Web 服务”。
    
3. 在“数据连接向导”对话框中，选择“接收数据”，然后单击“下一步”。
    
4. 键入包含示例 Web 服务方法的 Web 服务的地址，然后单击“下一步”。 
    
5. 对于接收方法，选择“getXhtml”操作形式，然后单击“下一步”。
    
6. **getXHTML** Web 服务方法不带任何参数，因此请单击“下一步”。
    
7. 单击“完成”。
    
8. 在“数据”选项卡上的“提交操作”组中，单击“至其他位置”，然后单击“Web 服务”以使用同一 Web 服务来提交数据。 
    
9. 键入包含示例 Web 服务方法的 Web 服务的地址，然后单击“下一步”。
    
10. 对于提交方法，选择“setXhtml”操作形式，然后单击“下一步”。
    
11. 单击“修改”，依次展开“dataFields”文件夹、“s0:getXhtmlResponse”文件夹和“getXhtmlResult”文件夹，选择“MyRichTextElement”元素，然后单击“下一步”。
    
12. 单击“完成”。
    
13. 在“字段”任务窗格中，展开“dataFields”文件夹。 
    
14. Expand the **s0:getXhtmlResponse** and **getXhtmlResult** folders, and then drag the **MyRichTextElement** element onto the form. InfoPath will recognize that the **MyRichTextElement** element is an XHTML element and will use a rich text box control to bind to it. 
    
15. 保存或发布表单。
    
To test the form, open the form, enter some rich text content such as pictures, tables, and formatted text. Click **Submit** on the ribbon to store the rich text content in the out.xml file on the server. Click **Query** on the **View** tab, and then click the **Run Query** button on the form. The **Rich Text Box** control should display the XHTML content from the out.xml file. If the rich text field contains multiple lines, the Web service will only accept the first line and ignore the rest. 
  

