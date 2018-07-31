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
# <a name="rich-text-and-web-services"></a><span data-ttu-id="64230-105">格式文本和 Web 服务</span><span class="sxs-lookup"><span data-stu-id="64230-105">Rich Text and Web Services</span></span>

<span data-ttu-id="64230-106">Microsoft InfoPath 支持将表单中的“格式文本框”**** 控件绑定到从 Web 服务收到的 XML 元素，以及通过 Web 服务将数据从格式文本框控件提交到 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="64230-106">Microsoft InfoPath supports binding a Rich Text Box control in a form to an XML element that is received from a Web service, and submitting data from a rich text box control to an XML element through a Web service.</span></span> <span data-ttu-id="64230-107">该元素必须遵循可扩展超文本标记语言 (XHTML) 格式。</span><span class="sxs-lookup"><span data-stu-id="64230-107">The element must adhere to the Extensible HyperText Markup Language (XHTML) format.</span></span> <span data-ttu-id="64230-108">例如，名为 `MyRichTextElement` 的元素（包含格式文本）的架构将具有以下 XML 架构定义：</span><span class="sxs-lookup"><span data-stu-id="64230-108">For example, the schema for an element named MyRichTextElement that contains rich text would have the following XML schema definition:</span></span> 
  
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

<span data-ttu-id="64230-109">应使用包装节点包装 XHTML 元素，然后才能将“格式文本框”**** 控件与该元素绑定；此包装节点可属于任何命名空间。</span><span class="sxs-lookup"><span data-stu-id="64230-109">Before a **Rich Text Box** control can be bound with the XHTML element, the element should be wrapped with a wrapper node; this wrapper node can belong to any arbitrary namespace. The wrapper node can look like this:</span></span> <span data-ttu-id="64230-110">包装节点可以如下所示：</span><span class="sxs-lookup"><span data-stu-id="64230-110">The wrapper node can look like this:</span></span> 
  
```xml
<xhtmlNode xmlns="http:// someNamespace"> 
    <div xmlns="http://www.w3.org/1999/xhtml">Your rich text here</div> 
</xhtmlNode>
```

<span data-ttu-id="64230-p104">本主题概述了创建可发送和接收 XHTML 的 Web 服务的过程，以及如何使用 InfoPath 来绑定到 Web 服务参数。本主题未提供有关如何创建此类 Web 服务的详细说明，并假定您已经熟悉如何使用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="64230-p104">This topic outlines the process of creating a Web service that can send and receive XHTML, and how to use InfoPath to bind to the Web service parameters. This topic does not provide detailed instructions on how to create such a Web service. It is assumed that you already have some familiarity with working with Web services.</span></span>
  
## <a name="how-to-design-a-web-service-to-receive-and-send-xhtml"></a><span data-ttu-id="64230-114">如何设计 Web 服务来接收和发送 XHTML</span><span class="sxs-lookup"><span data-stu-id="64230-114">How to Design a Web Service to Receive and Send XHTML</span></span>

<span data-ttu-id="64230-p105">示例 Web 服务将其发送和接收的 XHTML 数据存储在服务器上的一个 XML 文件中。名为 out.xml 的此文件充当存储 XHTML 数据的数据源。将公开以下两个 Web 方法，以允许客户端应用程序与 XHTML 数据源协调工作： `getXhtml` 和  `setXhtml`。 `getXhtml` Web 服务方法返回一个 **XmlNode**，其中包含可绑定到 InfoPath 格式文本框控件的 XHTML。 `setXhtml` Web 服务方法接受 **XmlNode** 作为数据以存储在 out.xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="64230-p105">The example Web service stores the XHTML data that it sends and receives in an XML file on the server. This file that is named out.xml, acts as a data source that stores the XHTML data. There are two Web methods that will be exposed to allow a client application to interface with the XHTML data source:  `getXhtml` and  `setXhtml`. The  `getXhtml` Web Service method returns an **XmlNode** that contains the XHTML that can be bound to an InfoPath rich text box control. The  `setXhtml` Web Service method accepts an **XmlNode** as the data to store in the out.xml file.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="64230-120">这些 Web 方法需要对 **System.IO** 和 **System.Xml** 命名空间进行引用的 **using** 语句。</span><span class="sxs-lookup"><span data-stu-id="64230-120">These Web methods require **using** statements that reference the **System.IO** and **System.Xml** namespaces.</span></span> 
  
<span data-ttu-id="64230-121">`getXhtml` Web 服务方法会尝试加载要从驱动器 C 上 Data 文件夹中的 out.xml 文件返回的 XML 数据。如果由于找不到文件或文件未包含有效的 XML 而失败，则该方法将返回一个引用 XHTML 命名空间的空 **DIV** HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="64230-121">The  `getXhtml` Web Service method attempts to load the XML data to be returned from the out.xml file in the Data folder on drive C. If it fails, because the file is not found, or does not contain valid XML, the method will return an empty **DIV** HTML element that references the XHTML namespace.</span></span> 
  
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

<span data-ttu-id="64230-122">`setXhtml` Web 服务方法接受出自 InfoPath 表单上的“格式文本框”**** 控件的 XHTML。</span><span class="sxs-lookup"><span data-stu-id="64230-122">The  `setXhtml` Web Service method accepts XHTML from a **Rich Text Box** control on an InfoPath form.</span></span> <span data-ttu-id="64230-123">由于 Web 服务不支持节点列表，因此，在将包含多行的格式文本字段发送到 Web 服务时，Web 服务将仅接受第一行，并忽略其余各行。</span><span class="sxs-lookup"><span data-stu-id="64230-123">The setXhtml Web Service method accepts XHTML from a Rich Text Box control on an ipnover2 form. Because Web services do not support a node list, when a rich text field that contains multiple lines is sent to a Web service, the Web service only accepts the first line and ignores the rest.</span></span> 
  
<span data-ttu-id="64230-124">示例 `setXhtml` 方法假定它将接收顶级 XML 节点，在大多数情况下，该节点将包含在 **DIV** 元素中。</span><span class="sxs-lookup"><span data-stu-id="64230-124">The sample  `setXhtml` method assumes that it will receive a top-level XML node, which in most cases will be wrapped in a **DIV** element.</span></span> <span data-ttu-id="64230-125">如果接收到的 XML 不包含包装元素，例如，当“格式文本框”**** 控件中的文本没有格式设置时，此方法将通过检查 **NodeType** 属性是否指示传入的 XML 为一个文本节点对其进行检测。</span><span class="sxs-lookup"><span data-stu-id="64230-125">If the XML received does not contain a wrapping element, for example when text within the **Rich Text Box** control has no formatting, this method will detect this by checking whether the **NodeType** property indicates that the XML passed in is a text node.</span></span> <span data-ttu-id="64230-126">如果 XML 是文本节点，则该方法将创建 **DIV** 元素并将文本节点内容复制到 **DIV**，以便 **DIV** 包含文本子节点（包含发送到 Web 服务的文本）。</span><span class="sxs-lookup"><span data-stu-id="64230-126">If the XML is a text node, the method creates a **DIV** element and copies the text node contents to the **DIV** so that the **DIV** contains a text node child with the text that was sent to the Web service.</span></span> <span data-ttu-id="64230-127">此方法接收的 XML 将写入驱动器 C 上数据文件夹中的 out.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="64230-127">The XML received by this method is written to the out.xml file in the Data folder on the drive C.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="64230-p108">编写示例  `setXhtml` 方法的目的是为了接受任何大小的 XHTML 数据。在实际应用中，您应始终检查以确定所提交的数据量，并为可提交的数据量设置一个上限。</span><span class="sxs-lookup"><span data-stu-id="64230-p108">The sample  `setXhtml` method was written to accept XHTML data of any size. In actual practice, you should always check to see how much data is being submitted and set an upper limit for how much data that can be submitted.</span></span> 
  
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

## <a name="how-to-create-an-infopath-form-that-exchanges-data-with-the-sample-web-service"></a><span data-ttu-id="64230-130">如何创建与示例 Web 服务交换数据的 InfoPath 表单</span><span class="sxs-lookup"><span data-stu-id="64230-130">How to Create an InfoPath Form That Exchanges Data with the Sample Web Service</span></span>

<span data-ttu-id="64230-131">执行以下步骤以创建一个表单来测试示例 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="64230-131">Perform the following steps to create a form to test the sample Web service.</span></span>
  
### <a name="to-create-a-form-that-connects-to-the-sample-web-service"></a><span data-ttu-id="64230-132">创建连接到示例 Web 服务的表单</span><span class="sxs-lookup"><span data-stu-id="64230-132">To create a form that connects to the sample Web service</span></span>

1. <span data-ttu-id="64230-133">打开 InfoPath 表单设计器。</span><span class="sxs-lookup"><span data-stu-id="64230-133">Open the InfoPath form designer.</span></span>
    
2. <span data-ttu-id="64230-134">在“新建”**** 选项卡上，双击“高级表单模板”**** 下的“Web 服务”****。</span><span class="sxs-lookup"><span data-stu-id="64230-134">On the **New** tab, double-click **Web Service** under **Advanced Form Templates**.</span></span>
    
3. <span data-ttu-id="64230-135">在“数据连接向导”**** 对话框中，选择“接收数据”****，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="64230-135">In the **Data Connection Wizard** dialog box, select **Receive data**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="64230-136">键入包含示例 Web 服务方法的 Web 服务的地址，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="64230-136">Type the address of the Web service that contains the sample Web service methods, and then click **Next**.</span></span> 
    
5. <span data-ttu-id="64230-137">对于接收方法，选择“getXhtml”**** 操作形式，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="64230-137">For the receive method, select **getXhtml** as the operation, and then click **Next**.</span></span>
    
6. <span data-ttu-id="64230-138">**getXHTML** Web 服务方法不带任何参数，因此请单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="64230-138">The **getXHTML** Web service method takes no parameters, so click **Next**.</span></span>
    
7. <span data-ttu-id="64230-139">单击“完成”****。</span><span class="sxs-lookup"><span data-stu-id="64230-139">Click **Finish**.</span></span>
    
8. <span data-ttu-id="64230-140">在“数据”**** 选项卡上的“提交操作”**** 组中，单击“至其他位置”****，然后单击“Web 服务”**** 以使用同一 Web 服务来提交数据。</span><span class="sxs-lookup"><span data-stu-id="64230-140">On the **Data** tab, in the **Submit Actions** group click **To Other Locations**, and then click **Web Service** to use the same Web service to the submit data.</span></span> 
    
9. <span data-ttu-id="64230-141">键入包含示例 Web 服务方法的 Web 服务的地址，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="64230-141">Type the address of the Web service that contains the sample Web service methods, and then click **Next**.</span></span>
    
10. <span data-ttu-id="64230-142">对于提交方法，选择“setXhtml”**** 操作形式，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="64230-142">For the submit method, select **setXhtml** as the operation, and then click **Next**.</span></span>
    
11. <span data-ttu-id="64230-143">单击“修改”****，依次展开“dataFields”**** 文件夹、“s0:getXhtmlResponse”**** 文件夹和“getXhtmlResult”**** 文件夹，选择“MyRichTextElement”**** 元素，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="64230-143">Click **Modify**, expand the **dataFields** folder, expand the**s0:getXhtmlResponse** folder, expand the **getXhtmlResult** folder, select the **MyRichTextElement** element, and then click **Next**.</span></span>
    
12. <span data-ttu-id="64230-144">单击“完成”****。</span><span class="sxs-lookup"><span data-stu-id="64230-144">Click **Finish**.</span></span>
    
13. <span data-ttu-id="64230-145">在“字段”**** 任务窗格中，展开“dataFields”**** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="64230-145">In the **Fields** task pane, expand the **dataFields** folder.</span></span> 
    
14. <span data-ttu-id="64230-146">展开“s0:getXhtmlResponse”**** 和“getXhtmlResult”**** 文件夹，然后将“MyRichTextElement”**** 元素拖到表单中。</span><span class="sxs-lookup"><span data-stu-id="64230-146">Expand the **s0:getXhtmlResponse** and **getXhtmlResult** folders, and then drag the **MyRichTextElement** element onto the form.</span></span> <span data-ttu-id="64230-147">InfoPath 将识别“MyRichTextElement”**** 元素为 XHTML 元素，并将使用格式文本框控件绑定到其中。</span><span class="sxs-lookup"><span data-stu-id="64230-147">Expand the s0:getXhtmlResponse and getXhtmlResult folders, and then drag the MyRichTextElement element onto the form. ipnover2 will recognize that the MyRichTextElement element is an XHTML element and will use a rich text box control to bind to it.</span></span> 
    
15. <span data-ttu-id="64230-148">保存或发布表单。</span><span class="sxs-lookup"><span data-stu-id="64230-148">Save or publish the form.</span></span>
    
<span data-ttu-id="64230-149">测试表单时，打开表单，输入一些格式文本内容，如图片、表格以及格式化文本。</span><span class="sxs-lookup"><span data-stu-id="64230-149">To test the form, open the form, enter some rich text content such as pictures, tables, and formatted text.</span></span> <span data-ttu-id="64230-150">单击功能区上的“提交”****，将格式文本内容存储在服务器上的 out.xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="64230-150">Click **Submit** on the ribbon to store the rich text content in the out.xml file on the server.</span></span> <span data-ttu-id="64230-151">单击“视图”**** 选项卡上的“查询”****，然后单击表单上的“运行查询”**** 按钮。</span><span class="sxs-lookup"><span data-stu-id="64230-151">Click **Query** on the **View** tab, and then click the **Run Query** button on the form.</span></span> <span data-ttu-id="64230-152">“格式文本框”**** 控件应显示 out.xml 文件中的 XHTML 内容。</span><span class="sxs-lookup"><span data-stu-id="64230-152">The **Rich Text Box** control should display the XHTML content from the out.xml file.</span></span> <span data-ttu-id="64230-153">如果格式文本字段包含多行，则 Web 服务将仅接受第一行，并忽略其余行。</span><span class="sxs-lookup"><span data-stu-id="64230-153">If the rich text field contains multiple lines, the Web service will only accept the first line and ignore the rest.</span></span> 
  
