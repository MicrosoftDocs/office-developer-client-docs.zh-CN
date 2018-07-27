---
title: 格式文本和 Web 服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 53fddc3f-e9d9-db76-6b84-11befdb23fb0
description: Microsoft InfoPath 支持将表单中的格式文本框控件绑定到从 Web 服务收到的 XML 元素，以及通过 Web 服务将数据从格式文本框控件提交到 XML 元素。该元素必须遵循可扩展超文本标记语言 (XHTML) 格式。例如，名为 MyRichTextElement 的元素（包含格式文本）的架构将具有以下 XML 架构定义：
ms.openlocfilehash: 07a7a3dbc0f054160adce54e316b01797feacd8a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774079"
---
# <a name="rich-text-and-web-services"></a>格式文本和 Web 服务

Microsoft InfoPath 支持将表单中的“格式文本框”**** 控件绑定到从 Web 服务收到的 XML 元素，以及通过 Web 服务将数据从格式文本框控件提交到 XML 元素。 该元素必须遵循可扩展超文本标记语言 (XHTML) 格式。 例如，名为 `MyRichTextElement` 的元素（包含格式文本）的架构将具有以下 XML 架构定义： 
  
```XML
<xsd:element name="MyRichTextElement"> 
    <xsd:complexType mixed="true"> 
        <xsd:sequence> 
            <xsd:any namespace="http://www.w3.org/1999/xhtml" processContents="lax" 
                minOccurs="0" maxOccurs="unbounded"/> 
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element>
```

应使用包装节点包装 XHTML 元素，然后才能将“格式文本框”**** 控件与该元素绑定；此包装节点可属于任何命名空间。 包装节点可以如下所示： 
  
```xml
<xhtmlNode xmlns="http:// someNamespace"> 
    <div xmlns="http://www.w3.org/1999/xhtml">Your rich text here</div> 
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
            // The "http://someNameSpace" can be any arbitrary namespace 
            XmlNode richNode = document.CreateNode 
                        (XmlNodeType.Element, "MyRichTextElement", "http://someNameSpace"); 
 
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
                tempDocument.LoadXml("<div xmlns=\"http://www.w3.org/1999/xhtml\"></div>"); 
            } 
 
            // Add the file content to the xml 
            richNode.AppendChild 
                        (document.ImportNode(tempDocument.DocumentElement, true)); 
 
            return richNode; 
}  

```

`setXhtml` Web 服务方法接受出自 InfoPath 表单上的“格式文本框”**** 控件的 XHTML。 由于 Web 服务不支持节点列表，因此，在将包含多行的格式文本字段发送到 Web 服务时，Web 服务将仅接受第一行，并忽略其余各行。 
  
示例 `setXhtml` 方法假定它将接收顶级 XML 节点，在大多数情况下，该节点将包含在 **DIV** 元素中。 如果接收到的 XML 不包含包装元素，例如，当“格式文本框”**** 控件中的文本没有格式设置时，此方法将通过检查 **NodeType** 属性是否指示传入的 XML 为一个文本节点对其进行检测。 如果 XML 是文本节点，则该方法将创建 **DIV** 元素并将文本节点内容复制到 **DIV**，以便 **DIV** 包含文本子节点（包含发送到 Web 服务的文本）。 此方法接收的 XML 将写入驱动器 C 上数据文件夹中的 out.xml 文件。 
  
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
                XmlElement div = document.CreateElement("div", "http://www.w3.org/1999/xhtml"); 
                // Copy the node to our own XmlDocument 
                document.AppendChild(div); 
            } 
            if (xn.NodeType == XmlNodeType.Text) 
            { 
                // If plain text is passed in, wrap it in a DIV 
                // that references the XHTML namespace 
                XmlElement div = document.CreateElement("div", "http://www.w3.org/1999/xhtml"); 
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
    
2. 在“新建”**** 选项卡上，双击“高级表单模板”**** 下的“Web 服务”****。
    
3. 在“数据连接向导”**** 对话框中，选择“接收数据”****，然后单击“下一步”****。
    
4. 键入包含示例 Web 服务方法的 Web 服务的地址，然后单击“下一步”****。 
    
5. 对于接收方法，选择“getXhtml”**** 操作形式，然后单击“下一步”****。
    
6. **getXHTML** Web 服务方法不带任何参数，因此请单击“下一步”****。
    
7. 单击“完成”****。
    
8. 在“数据”**** 选项卡上的“提交操作”**** 组中，单击“至其他位置”****，然后单击“Web 服务”**** 以使用同一 Web 服务来提交数据。 
    
9. 键入包含示例 Web 服务方法的 Web 服务的地址，然后单击“下一步”****。
    
10. 对于提交方法，选择“setXhtml”**** 操作形式，然后单击“下一步”****。
    
11. 单击“修改”****，依次展开“dataFields”**** 文件夹、“s0:getXhtmlResponse”**** 文件夹和“getXhtmlResult”**** 文件夹，选择“MyRichTextElement”**** 元素，然后单击“下一步”****。
    
12. 单击“完成”****。
    
13. 在“字段”**** 任务窗格中，展开“dataFields”**** 文件夹。 
    
14. 展开“s0:getXhtmlResponse”**** 和“getXhtmlResult”**** 文件夹，然后将“MyRichTextElement”**** 元素拖到表单中。 InfoPath 将识别“MyRichTextElement”**** 元素为 XHTML 元素，并将使用格式文本框控件绑定到其中。 
    
15. 保存或发布表单。
    
测试表单时，打开表单，输入一些格式文本内容，如图片、表格以及格式化文本。 单击功能区上的“提交”****，将格式文本内容存储在服务器上的 out.xml 文件中。 单击“视图”**** 选项卡上的“查询”****，然后单击表单上的“运行查询”**** 按钮。 “格式文本框”**** 控件应显示 out.xml 文件中的 XHTML 内容。 如果格式文本字段包含多行，则 Web 服务将仅接受第一行，并忽略其余行。 
  

