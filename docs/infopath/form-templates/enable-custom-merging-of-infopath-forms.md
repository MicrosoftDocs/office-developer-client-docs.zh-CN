---
title: 启用 InfoPath 表单的自定义合并
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: f08f9212-af10-1287-477d-adde7674f523
description: Microsoft InfoPath 编辑器的“合并表单”功能旨在将多个表单中的数据合并到一个表单。
ms.openlocfilehash: f79553f7fdf0b59c77a98fd479e0a307e4f2e6a3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537799"
---
# <a name="enable-custom-merging-of-infopath-forms"></a>启用 InfoPath 表单的自定义合并

The **Merge Forms** feature of the Microsoft InfoPath editor is designed to combine the data from multiple forms into a single form. This is also known as data aggregation. If merging forms is enabled, you can click the **File** tab, click **Save &amp; Send**, click **Merge Forms** under **Import &amp; Link**, and then click the **Merge Forms** button to select one or more forms to merge with the currently opened form. The form that is currently open is the target form and the forms selected in the **Merge Forms** dialog box are known as the source forms.
  
通过合并表单生成的数据的聚合可以包括源表单和目标表单中包含的所有数据，或者仅包括原始数据的一部分。默认操作如下。
  
- 对于重复元素，将在目标文档中的匹配位置插入数据。当目标元素的 **MaxOccurs** 属性大于 1 时，将发生这种情况。 
    
- 对于非重复元素（即 **MaxOccurs** 为"1"的元素），会将源元素的属性添加到目标元素的现有属性。 
    
## <a name="creating-a-custom-transform"></a>创建自定义转换

合并表单时的默认操作非常适合于基于相同 XML 架构的表单。但是，在某些情况下，您可能需要合并基于不同架构的表单，或者为基于相同架构的表单覆盖默认合并操作。对于这些方案，您可以创建一个 XSL 转换 (XSLT)，其中包含用于合并操作的聚合指令。将在合并时应用该转换，以创建一个 DOM 文档，该文档包含要导入的信息，以及指定如何将此信息并入目标文档的注释。这些注释是命名空间  `http://schemas.microsoft.com/office/InfoPath/2003/aggregation` 中的 XML 属性。
  
这些 XML 属性及其值充当有关如何将每个节点与目标 XML 文档合并的聚合指令。以下各节中描述了这些属性。
  
### <a name="select"></a>select

**agg:select** 属性包含标识目标元素的绝对 XPath 表达式。 
  
### <a name="insert"></a>insert

**agg:action** 属性的"insert"值指示 InfoPath 将源元素作为目标元素的子项插入，目标元素是使用 **agg:select** 属性指定的。源元素的子项包括在插入操作中。 **selectChild** 属性允许您为插入节点操作选择某个位置。 **order** 属性用于指定是将源元素插入在现有目标元素之前还是之后。如果 **order** 属性不存在，则默认值为"after"。 
  
```XML
<my:field1 agg:select="/my:myFields/my:field1"
 agg:action="insert" agg:order="before">Some Value</my:field1>

```

### <a name="replace"></a>replace

**agg:action** 属性的"replace"值指示 InfoPath 将 **select** 属性引用的每个目标元素替换为源元素。 
  
```XML
<my:field1 agg:select="/my:myFields/my:field1"
 agg:action="replace">Some Value</my:field1>
```

### <a name="mergeattributes"></a>mergeAttributes

如果 **agg:action** 属性的值为"mergeAttributes"，则源元素的属性将与 **select** 属性引用的每个目标元素的属性合并。 
  
```XML
<my:PMAwS agg:action="mergeAttributes"
 agg:select="/my:Root/my:PMAwS">
```

### <a name="delete"></a>delete

如果 **agg:action** 属性的值为"delete"，则会从目标文档中删除 **select** 属性引用的每个目标元素。 
  
```XML
<my:field1 agg:select="/my:myFields/my:field1"
 agg:action="delete"/>
```

结合  `http://schemas.microsoft.com/office/InfoPath/2003/aggregation` 命名空间中指定的属性，可以使用  `http://schemas.microsoft.com/office/infopath/2003/aggregation-target` 命名空间来指示实现接口 **IXMLDOMDocument** 的 XSL 对象。此接口最有用的成员之一是方法 **get-documentElement**。
  
### <a name="get-documentelement"></a>get-documentElement

**target:get-documentElement** 函数提供对目标文档的文档对象模型的访问。可以使用该函数来更改合并操作处理目标文档的当前内容的方式。 
  
```XML
<xsl:when test="function-available('target:get-documentElement')">
    <xsl:variable name="target" select="target:get-documentElement()" />
    <xsl:if test="not(boolean($target/my:Customer[Name="MyName"]))">
        <my:Customer agg:action="insert" agg:select="/my:MergeForms" />
    </xsl:if>
</xsl:when>

```

## <a name="steps-for-creating-a-custom-merge"></a>创建自定义合并的步骤

1. 选择要从中合并数据的 XML 源文档的种类。收集每种源文档的代表性示例。
    
2. Derive the XML schema for each kind of XML source document for an existing InfoPath form. This step is easily accomplished by exporting the XML schema with the **Export Source Files** command on the **Publish** tab of the Backstage. For XML documents that were not created in InfoPath, you can use a tool such as Microsoft Visual Studio to create a schema from the sample XML document, or you can create a sample form from the XML document in InfoPath, and then export the schema that InfoPath derives from the document structure. 
    
3. 确定要从每种 XML 源文档中合并的数据。此步骤将几乎完全取决于源表单和目标表单的要求。对于某些表单，您可能需要从源表单中复制所有数据。对于其他表单，则可能只需要从表单的基础 XML 文档中复制一两个元素。在确定要合并什么数据时，要格外留意源文档和目标文档，以确保元素在两个表单之间有逻辑地映射。
    
4. 为每种 XML 源文档创建 XSL 转换。在配置表单的合并时，此步骤将花费大部分时间。XSL 转换的目的是将源 XML 文档转换为可与目标表单合并的格式。在设计转换时，要决定是要使用通过 XML 位置路径进行的合并，还是使用通过 InfoPath 聚合指令进行的合并。
    
    利用 Visual Studio 工具可以方便地创建 XSL 转换。Visual Studio 提供了语法颜色设置和文档大纲。它还能自动为 XSL 元素提供结束标记，从而可帮助减少冗长的键入和难于查找的拼写错误。也可以使用诸如记事本等文本编辑器来创建 XSL 转换。
    
    首先创建标识转换，该转换仅仅是一个输出相同 XSL 文件（作为输入）的 XSL 转换：
    
    ```XML
        <?xml version="1.0"?> 
        <xsl:stylesheet version="1.0" xmlns:xsl="https://www.w3.org/1999/XSL/Transform" 
        xmlns:agg="http://schemas.microsoft.com/office/infopath/2003/aggregation" 
        xmlns:target="http://schemas.microsoft.com/office/infopath/2003/aggregation-target" 
        xmlns:my="http://schemas.microsoft.com/office/infopath/2003/myXSD/2003-05-29T20:30:47"> 
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

    然后，为要增加特殊处理的元素添加替代模板节。例如，此模板将  `<src:Task>` 元素更改为  `<my:field1>` 元素，并将 **agg:action** 属性的值设置为"replace"。 
    
    ```XML
        <xsl:template match="src:Task"> 
            <my:field1 agg:select="/my:myFields/my:field1" agg:action="replace"> 
                <xsl:value-of select="."/> 
            </my:field1> 
        </xsl:template>
    ```

5. Add the XSL transform files and schema files in the form template. After you have derived schemas for each kind of source document and created an XSL transform to convert each document type so that InfoPath can merge its data, add them to as resources to your form. Click **Resource Files** on the **Data** tab, and then click **Add** in the **Resource Files** dialog box, browse to your schema or XSL transform file, and then click **OK**. Do this to for each schema file and XSL transform file that you created.
    
    If the schemas that you add use the **targetNamespace** attribute, you must add a property element to the form's .xsf file so that InfoPath knows the namespace of the schema. To access this file, click the **File** tab, click **Publish**, and then click **Export Source Files**. Select a location for the files, and then click **OK**. Then close the InfoPath form template that you are designing.
    
    浏览到您为提取的文件指定的位置，并查找具有 .xsf 文件扩展名的文件。通常，此文件名为 manifest.xsf。在记事本中打开该文件，查找与您的架构对应的  `<xsf:file>` 标记，并添加"namespace"属性元素以指定 **targetNamespace**，如下面的示例所示。 
    
    ```xml
        <xsf:file name="IndvTasks.xsd"> 
            <xsf:fileProperties> 
                <xsf:property name="fileType" type="string" value="Resource" /> 
                <xsf:property name="namespace" type="string" 
                value="urn:office-microsoft-com:InfoPath-designer-aggregation-IndStatusReport" /> 
            </xsf:fileProperties> 
        </xsf:file>
    ```

6. 准备表单以支持自定义合并的最后一步是更新 .xsf 文件中与表单关联的 **importParameters** 元素。 

    首先，在 .xsf 文件中找到 `<xsf:importParameters>` 标记。 对于为表单创建的每个架构/XSL 转换对，将 **xsf:importSource** 元素添加到 **xsf:importParameters** 元素：`<xsf:importParameters enabled="yes"> <xsf:importSource name="" schema="IndvTasks.xsd" transform="ImportTasks.xsl"></xsf:importSource> </xsf:importParameters>`。 
    
    **xsf:importSource** 元素的 **name** 属性包含可在源 XML 文档中找到的表单模板名称。 通常情况下，你可以将它留空。 **schema** 属性包含在上一步中添加到表单模板的架构文件的名称。 最后， **transform** 属性包含要用于转换符合架构的表单的 XSL 转换的名称。 
    
    您可以将自定义转换与 [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) 事件一起使用，也可以单独使用自定义转换。 
    
## <a name="creating-a-custom-merge-in-code"></a>在代码中创建自定义合并

通过使用 [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) 事件处理程序可以支持自定义与代码的合并，其中 .xsf 文件中 **importParameters** 元素的相应的 **useScriptHandler** 属性与表单相关联。 

In managed code, you can enable the [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) event by checking the box **Merge using custom code**, and then clicking the **Edit** button, in the **Advanced** category of the **Form Options** dialog box available from the Backstage. 
  

