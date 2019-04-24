---
title: 启用 InfoPath 表单的自定义合并
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: f08f9212-af10-1287-477d-adde7674f523
description: Microsoft InfoPath 编辑器的“合并表单”功能旨在将多个表单中的数据合并到一个表单。
ms.openlocfilehash: 598c44bfe63a31237bf82ceb2212b001fbe7cc1f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303722"
---
# <a name="enable-custom-merging-of-infopath-forms"></a><span data-ttu-id="03787-103">启用 InfoPath 表单的自定义合并</span><span class="sxs-lookup"><span data-stu-id="03787-103">Enable Custom Merging of InfoPath Forms</span></span>

<span data-ttu-id="03787-p101">The **Merge Forms** feature of the Microsoft InfoPath editor is designed to combine the data from multiple forms into a single form. This is also known as data aggregation. If merging forms is enabled, you can click the **File** tab, click **Save &amp; Send**, click **Merge Forms** under **Import &amp; Link**, and then click the **Merge Forms** button to select one or more forms to merge with the currently opened form. The form that is currently open is the target form and the forms selected in the **Merge Forms** dialog box are known as the source forms.</span><span class="sxs-lookup"><span data-stu-id="03787-p101">The **Merge Forms** feature of the Microsoft InfoPath editor is designed to combine the data from multiple forms into a single form. This is also known as data aggregation. If merging forms is enabled, you can click the **File** tab, click **Save &amp; Send**, click **Merge Forms** under **Import &amp; Link**, and then click the **Merge Forms** button to select one or more forms to merge with the currently opened form. The form that is currently open is the target form and the forms selected in the **Merge Forms** dialog box are known as the source forms.</span></span>
  
<span data-ttu-id="03787-p102">通过合并表单生成的数据的聚合可以包括源表单和目标表单中包含的所有数据，或者仅包括原始数据的一部分。默认操作如下。</span><span class="sxs-lookup"><span data-stu-id="03787-p102">The aggregation of data that results from merging forms can include all of the data that is contained in the source and target forms, or only a portion of the original data. The default operations are the following.</span></span>
  
- <span data-ttu-id="03787-p103">对于重复元素，将在目标文档中的匹配位置插入数据。当目标元素的 **MaxOccurs** 属性大于 1 时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="03787-p103">For repeating elements, data is inserted at a matching location in the target document. This happens when the **MaxOccurs** attribute of the destination element is greater than 1.</span></span> 
    
- <span data-ttu-id="03787-112">对于非重复元素（即 **MaxOccurs** 为"1"的元素），会将源元素的属性添加到目标元素的现有属性。</span><span class="sxs-lookup"><span data-stu-id="03787-112">For non-repeating elements (that is, for elements where **MaxOccurs** is "1"), the attributes of the source elements are added to the existing attributes of the destination element.</span></span> 
    
## <a name="creating-a-custom-transform"></a><span data-ttu-id="03787-113">创建自定义转换</span><span class="sxs-lookup"><span data-stu-id="03787-113">Creating a Custom Transform</span></span>

<span data-ttu-id="03787-p104">合并表单时的默认操作非常适合于基于相同 XML 架构的表单。但是，在某些情况下，您可能需要合并基于不同架构的表单，或者为基于相同架构的表单覆盖默认合并操作。对于这些方案，您可以创建一个 XSL 转换 (XSLT)，其中包含用于合并操作的聚合指令。将在合并时应用该转换，以创建一个 DOM 文档，该文档包含要导入的信息，以及指定如何将此信息并入目标文档的注释。这些注释是命名空间  `https://schemas.microsoft.com/office/InfoPath/2003/aggregation` 中的 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="03787-p104">The default operation when merging forms works well for forms that are based on the same XML schema. In some circumstances, however, you may want to merge forms that are based on different schemas or override the default merge operation for forms that are based on the same schema. For these scenarios, you can create an XSL Transform (XSLT), which contains aggregation instructions for the merge operation. The transform is applied at merge time to create a DOM document that contains the information to be imported, together with annotations specifying how to incorporate this information into the target document. These annotations are XML attributes in the namespace  `https://schemas.microsoft.com/office/InfoPath/2003/aggregation`.</span></span>
  
<span data-ttu-id="03787-p105">这些 XML 属性及其值充当有关如何将每个节点与目标 XML 文档合并的聚合指令。以下各节中描述了这些属性。</span><span class="sxs-lookup"><span data-stu-id="03787-p105">The XML attributes and their values serve as aggregation instructions on how each node is merged with the destination XML document. These attributes are described in the following sections.</span></span>
  
### <a name="select"></a><span data-ttu-id="03787-121">select</span><span class="sxs-lookup"><span data-stu-id="03787-121">select</span></span>

<span data-ttu-id="03787-122">**agg:select** 属性包含标识目标元素的绝对 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="03787-122">The **agg:select** attribute contains an absolute XPath expression which identifies the destination element.</span></span> 
  
### <a name="insert"></a><span data-ttu-id="03787-123">insert</span><span class="sxs-lookup"><span data-stu-id="03787-123">insert</span></span>

<span data-ttu-id="03787-p106">**agg:action** 属性的"insert"值指示 InfoPath 将源元素作为目标元素的子项插入，目标元素是使用 **agg:select** 属性指定的。源元素的子项包括在插入操作中。 **selectChild** 属性允许您为插入节点操作选择某个位置。 **order** 属性用于指定是将源元素插入在现有目标元素之前还是之后。如果 **order** 属性不存在，则默认值为"after"。</span><span class="sxs-lookup"><span data-stu-id="03787-p106">A value of "insert" for the **agg:action** attribute instructs InfoPath to insert the source element as a child of the destination element that is specified by using the **agg:select** attribute. The children of the source element are included in the insert operation. The **selectChild** attribute lets you select a certain location for the insert node operation. The **order** attribute is used to specify whether the source elements are inserted before existing destination elements or after. The default value if the **order** attribute is not present is "after".</span></span> 
  
```XML
<my:field1 agg:select="/my:myFields/my:field1"
 agg:action="insert" agg:order="before">Some Value</my:field1>

```

### <a name="replace"></a><span data-ttu-id="03787-129">replace</span><span class="sxs-lookup"><span data-stu-id="03787-129">replace</span></span>

<span data-ttu-id="03787-130">**agg:action** 属性的"replace"值指示 InfoPath 将 **select** 属性引用的每个目标元素替换为源元素。</span><span class="sxs-lookup"><span data-stu-id="03787-130">A value of "replace" for the **agg:action** attribute instructs InfoPath to replace each of the destination elements referred to by the **select** attribute with the source element.</span></span> 
  
```XML
<my:field1 agg:select="/my:myFields/my:field1"
 agg:action="replace">Some Value</my:field1>
```

### <a name="mergeattributes"></a><span data-ttu-id="03787-131">mergeAttributes</span><span class="sxs-lookup"><span data-stu-id="03787-131">mergeAttributes</span></span>

<span data-ttu-id="03787-132">如果 **agg:action** 属性的值为"mergeAttributes"，则源元素的属性将与 **select** 属性引用的每个目标元素的属性合并。</span><span class="sxs-lookup"><span data-stu-id="03787-132">If the value of the **agg:action** attribute is "mergeAttributes", the attributes of the source element are merged with the attributes of each of the destination elements referred to by the **select** attribute.</span></span> 
  
```XML
<my:PMAwS agg:action="mergeAttributes"
 agg:select="/my:Root/my:PMAwS">
```

### <a name="delete"></a><span data-ttu-id="03787-133">delete</span><span class="sxs-lookup"><span data-stu-id="03787-133">delete</span></span>

<span data-ttu-id="03787-134">如果 **agg:action** 属性的值为"delete"，则会从目标文档中删除 **select** 属性引用的每个目标元素。</span><span class="sxs-lookup"><span data-stu-id="03787-134">If the value of the **agg:action** attribute is "delete", each of the destination elements referred to by the **select** attribute are deleted from the destination document.</span></span> 
  
```XML
<my:field1 agg:select="/my:myFields/my:field1"
 agg:action="delete"/>
```

<span data-ttu-id="03787-p107">结合  `https://schemas.microsoft.com/office/InfoPath/2003/aggregation` 命名空间中指定的属性，可以使用  `https://schemas.microsoft.com/office/infopath/2003/aggregation-target` 命名空间来指示实现接口 **IXMLDOMDocument** 的 XSL 对象。此接口最有用的成员之一是方法 **get-documentElement**。</span><span class="sxs-lookup"><span data-stu-id="03787-p107">In conjunction with the attributes specified in the  `https://schemas.microsoft.com/office/InfoPath/2003/aggregation` namespace, you use the  `https://schemas.microsoft.com/office/infopath/2003/aggregation-target` namespace to denote an XSL object that implements the interface **IXMLDOMDocument**. One of the most useful members of this interface is the method **get-documentElement**.</span></span>
  
### <a name="get-documentelement"></a><span data-ttu-id="03787-137">get-documentElement</span><span class="sxs-lookup"><span data-stu-id="03787-137">get-documentElement</span></span>

<span data-ttu-id="03787-p108">**target:get-documentElement** 函数提供对目标文档的文档对象模型的访问。可以使用该函数来更改合并操作处理目标文档的当前内容的方式。</span><span class="sxs-lookup"><span data-stu-id="03787-p108">The **target:get-documentElement** function provides access to the Document Object Model of the destination document. It can be used to change the way the merge operation works based on the current contents of the destination document.</span></span> 
  
```XML
<xsl:when test="function-available('target:get-documentElement')">
    <xsl:variable name="target" select="target:get-documentElement()" />
    <xsl:if test="not(boolean($target/my:Customer[Name="MyName"]))">
        <my:Customer agg:action="insert" agg:select="/my:MergeForms" />
    </xsl:if>
</xsl:when>

```

## <a name="steps-for-creating-a-custom-merge"></a><span data-ttu-id="03787-140">创建自定义合并的步骤</span><span class="sxs-lookup"><span data-stu-id="03787-140">Steps for Creating a Custom Merge</span></span>

1. <span data-ttu-id="03787-p109">选择要从中合并数据的 XML 源文档的种类。收集每种源文档的代表性示例。</span><span class="sxs-lookup"><span data-stu-id="03787-p109">Select the kinds of XML source documents from which you want to merge data. Collect a representative sample of each kind of source document.</span></span>
    
2. <span data-ttu-id="03787-p110">Derive the XML schema for each kind of XML source document for an existing InfoPath form. This step is easily accomplished by exporting the XML schema with the **Export Source Files** command on the **Publish** tab of the Backstage. For XML documents that were not created in InfoPath, you can use a tool such as Microsoft Visual Studio to create a schema from the sample XML document, or you can create a sample form from the XML document in InfoPath, and then export the schema that InfoPath derives from the document structure.</span><span class="sxs-lookup"><span data-stu-id="03787-p110">Derive the XML schema for each kind of XML source document for an existing InfoPath form. This step is easily accomplished by exporting the XML schema with the **Export Source Files** command on the **Publish** tab of the Backstage. For XML documents that were not created in InfoPath, you can use a tool such as Microsoft Visual Studio to create a schema from the sample XML document, or you can create a sample form from the XML document in InfoPath, and then export the schema that InfoPath derives from the document structure.</span></span> 
    
3. <span data-ttu-id="03787-p111">确定要从每种 XML 源文档中合并的数据。此步骤将几乎完全取决于源表单和目标表单的要求。对于某些表单，您可能需要从源表单中复制所有数据。对于其他表单，则可能只需要从表单的基础 XML 文档中复制一两个元素。在确定要合并什么数据时，要格外留意源文档和目标文档，以确保元素在两个表单之间有逻辑地映射。</span><span class="sxs-lookup"><span data-stu-id="03787-p111">Identify the data that you want to merge from each kind of XML source document. This step will depend almost entirely on the requirements of both your source and destination forms. For some forms, you may want to copy all of the data from the source form. For others, you may want only one or two elements from the form's underlying XML document. When identifying what data that you want to merge, pay extra attention to both the source and destination documents to ensure that the elements map logically between the two forms.</span></span>
    
4. <span data-ttu-id="03787-p112">为每种 XML 源文档创建 XSL 转换。在配置表单的合并时，此步骤将花费大部分时间。XSL 转换的目的是将源 XML 文档转换为可与目标表单合并的格式。在设计转换时，要决定是要使用通过 XML 位置路径进行的合并，还是使用通过 InfoPath 聚合指令进行的合并。</span><span class="sxs-lookup"><span data-stu-id="03787-p112">Create an XSL transform for each kind of XML source document. When configuring the merging of your forms, this step will take the most time. The purpose of the XSL transform is to transform the source XML document into a format that can be merged with the destination form. When designing your transform, decide whether you want to use merging from XML location paths, or merging from InfoPath aggregation instructions.</span></span>
    
    <span data-ttu-id="03787-p113">利用 Visual Studio 工具可以方便地创建 XSL 转换。Visual Studio 提供了语法颜色设置和文档大纲。它还能自动为 XSL 元素提供结束标记，从而可帮助减少冗长的键入和难于查找的拼写错误。也可以使用诸如记事本等文本编辑器来创建 XSL 转换。</span><span class="sxs-lookup"><span data-stu-id="03787-p113">Visual Studio is a convenient tool for creating XSL transforms. Visual Studio provides syntax coloring and a document outline. It also automatically provides closing tags for your XSL elements, which can help decrease redundant typing and hard-to-find spelling errors. You can also create XSL transforms with a text editor such as Notepad.</span></span>
    
    <span data-ttu-id="03787-159">首先创建标识转换，该转换仅仅是一个输出相同 XSL 文件（作为输入）的 XSL 转换：</span><span class="sxs-lookup"><span data-stu-id="03787-159">Start with the identity transform, which is simply an XSL transform that outputs the same XML file that is input:</span></span>
    
    ```XML
        <?xml version="1.0"?> 
        <xsl:stylesheet version="1.0" xmlns:xsl="https://www.w3.org/1999/XSL/Transform" 
        xmlns:agg="https://schemas.microsoft.com/office/infopath/2003/aggregation" 
        xmlns:target="https://schemas.microsoft.com/office/infopath/2003/aggregation-target" 
        xmlns:my="https://schemas.microsoft.com/office/infopath/2003/myXSD/2003-05-29T20:30:47"> 
            <xsl:template match="/"> 
                <xsl:copy> 
                <xsl:apply-templates select="@* | node()" /> 
                </xsl:copy> 
            </xsl:template> 
            <xsl:template match="@* | node()"> 
                <xsl:copy> 
                <xsl:apply-templates select="@* | node()" /> 
                </xsl:copy> 
            </xsl:template> 
        </xsl:stylesheet>
    ```

    <span data-ttu-id="03787-p114">然后，为要增加特殊处理的元素添加替代模板节。例如，此模板将  `<src:Task>` 元素更改为  `<my:field1>` 元素，并将 **agg:action** 属性的值设置为"replace"。</span><span class="sxs-lookup"><span data-stu-id="03787-p114">Then add overriding template sections for the elements you want to add special handling for. For example, this template changes a  `<src:Task>` element into a  `<my:field1>` element and sets the value of the **agg:action** attribute to "replace".</span></span> 
    
    ```XML
        <xsl:template match="src:Task"> 
            <my:field1 agg:select="/my:myFields/my:field1" agg:action="replace"> 
                <xsl:value-of select="."/> 
            </my:field1> 
        </xsl:template>
    ```

5. <span data-ttu-id="03787-p115">Add the XSL transform files and schema files in the form template. After you have derived schemas for each kind of source document and created an XSL transform to convert each document type so that InfoPath can merge its data, add them to as resources to your form. Click **Resource Files** on the **Data** tab, and then click **Add** in the **Resource Files** dialog box, browse to your schema or XSL transform file, and then click **OK**. Do this to for each schema file and XSL transform file that you created.</span><span class="sxs-lookup"><span data-stu-id="03787-p115">Add the XSL transform files and schema files in the form template. After you have derived schemas for each kind of source document and created an XSL transform to convert each document type so that InfoPath can merge its data, add them to as resources to your form. Click **Resource Files** on the **Data** tab, and then click **Add** in the **Resource Files** dialog box, browse to your schema or XSL transform file, and then click **OK**. Do this to for each schema file and XSL transform file that you created.</span></span>
    
    <span data-ttu-id="03787-p116">If the schemas that you add use the **targetNamespace** attribute, you must add a property element to the form's .xsf file so that InfoPath knows the namespace of the schema. To access this file, click the **File** tab, click **Publish**, and then click **Export Source Files**. Select a location for the files, and then click **OK**. Then close the InfoPath form template that you are designing.</span><span class="sxs-lookup"><span data-stu-id="03787-p116">If the schemas that you add use the **targetNamespace** attribute, you must add a property element to the form's .xsf file so that InfoPath knows the namespace of the schema. To access this file, click the **File** tab, click **Publish**, and then click **Export Source Files**. Select a location for the files, and then click **OK**. Then close the InfoPath form template that you are designing.</span></span>
    
    <span data-ttu-id="03787-p117">浏览到您为提取的文件指定的位置，并查找具有 .xsf 文件扩展名的文件。通常，此文件名为 manifest.xsf。在记事本中打开该文件，查找与您的架构对应的  `<xsf:file>` 标记，并添加"namespace"属性元素以指定 **targetNamespace**，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="03787-p117">Browse to the location that you specified for the extracted files and find the file that has an .xsf file name extension. Usually, this file is called manifest.xsf. Open the file in Notepad, find the  `<xsf:file>` tag that corresponds to your schema, and add a "namespace" property element to specify the **targetNamespace** as shown in the following example.</span></span> 
    
    ```xml
        <xsf:file name="IndvTasks.xsd"> 
            <xsf:fileProperties> 
                <xsf:property name="fileType" type="string" value="Resource" /> 
                <xsf:property name="namespace" type="string" 
                value="urn:office-microsoft-com:InfoPath-designer-aggregation-IndStatusReport" /> 
            </xsf:fileProperties> 
        </xsf:file>
    ```

6. <span data-ttu-id="03787-173">准备表单以支持自定义合并的最后一步是更新 .xsf 文件中与表单关联的 **importParameters** 元素。</span><span class="sxs-lookup"><span data-stu-id="03787-173">The last step in preparing your form to support custom merging is to update the **importParameters** element in the .xsf file associated with the form.</span></span> 

    <span data-ttu-id="03787-174">首先，在 .xsf 文件中找到 `<xsf:importParameters>` 标记。</span><span class="sxs-lookup"><span data-stu-id="03787-174">First, find the  `<xsf:importParameters>` tag in the .xsf file.</span></span> <span data-ttu-id="03787-175">对于为表单创建的每个架构/XSL 转换对，将 **xsf:importSource** 元素添加到 **xsf:importParameters** 元素：`<xsf:importParameters enabled="yes"> <xsf:importSource name="" schema="IndvTasks.xsd" transform="ImportTasks.xsl"></xsf:importSource> </xsf:importParameters>`。</span><span class="sxs-lookup"><span data-stu-id="03787-175">For each schema/XSL transform pair you have created for your form, add an **xsf:importSource** element to the **xsf:importParameters** element:  `<xsf:importParameters enabled="yes"> <xsf:importSource name="" schema="IndvTasks.xsd" transform="ImportTasks.xsl"></xsf:importSource> </xsf:importParameters>`.</span></span> 
    
    <span data-ttu-id="03787-176">**xsf:importSource** 元素的 **name** 属性包含可在源 XML 文档中找到的表单模板名称。</span><span class="sxs-lookup"><span data-stu-id="03787-176">The **name** attribute of the **xsf:importSource** element contains the form template's name that may be found in a source XML document.</span></span> <span data-ttu-id="03787-177">通常情况下，你可以将它留空。</span><span class="sxs-lookup"><span data-stu-id="03787-177">Usually, you can leave this empty.</span></span> <span data-ttu-id="03787-178">**schema** 属性包含在上一步中添加到表单模板的架构文件的名称。</span><span class="sxs-lookup"><span data-stu-id="03787-178">The **schema** attribute contains the name of a schema file that you added to the form template in the previous step.</span></span> <span data-ttu-id="03787-179">最后， **transform** 属性包含要用于转换符合架构的表单的 XSL 转换的名称。</span><span class="sxs-lookup"><span data-stu-id="03787-179">Finally, the **transform** attribute contains the name of the XSL transform that you want to use to convert forms that conform to the schema.</span></span> 
    
    <span data-ttu-id="03787-180">您可以将自定义转换与 [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) 事件一起使用，也可以单独使用自定义转换。</span><span class="sxs-lookup"><span data-stu-id="03787-180">You can use a custom transform either with the [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) event or on its own.</span></span> 
    
## <a name="creating-a-custom-merge-in-code"></a><span data-ttu-id="03787-181">在代码中创建自定义合并</span><span class="sxs-lookup"><span data-stu-id="03787-181">Creating a Custom Merge in Code</span></span>

<span data-ttu-id="03787-182">通过使用 [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) 事件处理程序可以支持自定义与代码的合并，其中 .xsf 文件中 **importParameters** 元素的相应的 **useScriptHandler** 属性与表单相关联。</span><span class="sxs-lookup"><span data-stu-id="03787-182">Custom merging with code is supported by using the [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) event handler, with its corresponding **useScriptHandler** attribute of the **importParameters** element in the .xsf file associated with the form.</span></span> 

<span data-ttu-id="03787-183">In managed code, you can enable the [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) event by checking the box **Merge using custom code**, and then clicking the **Edit** button, in the **Advanced** category of the **Form Options** dialog box available from the Backstage.</span><span class="sxs-lookup"><span data-stu-id="03787-183">In managed code, you can enable the [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) event by checking the box **Merge using custom code**, and then clicking the **Edit** button, in the **Advanced** category of the **Form Options** dialog box available from the Backstage.</span></span> 
  

