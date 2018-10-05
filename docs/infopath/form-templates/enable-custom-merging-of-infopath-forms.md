---
title: 启用 InfoPath 表单的自定义合并
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: f08f9212-af10-1287-477d-adde7674f523
description: Microsoft InfoPath 编辑器的“合并表单”功能旨在将多个表单中的数据合并到一个表单。
ms.openlocfilehash: 598c44bfe63a31237bf82ceb2212b001fbe7cc1f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386913"
---
# <a name="enable-custom-merging-of-infopath-forms"></a>启用 InfoPath 表单的自定义合并

Microsoft InfoPath 编辑器的“合并表单”**** 功能旨在将多个表单中的数据合并到一个表单。 这也称为“数据聚合”。 如果启用了合并表单功能，则可以单击“文件”**** 选项卡，单击“保存并发送”****，单击“导入和链接”**** 下的“合并表单”****，然后单击“合并表单”**** 按钮以选择一个或多个要与当前打开的表单合并的表单。 当前处于打开状态的表单是目标表单，在“合并表单”**** 对话框中选择的表单称为源表单。
  
通过合并表单生成的数据的聚合可以包括源表单和目标表单中包含的所有数据，或者仅包括原始数据的一部分。默认操作如下。
  
- 对于重复元素，将在目标文档中的匹配位置插入数据。当目标元素的 **MaxOccurs** 属性大于 1 时，将发生这种情况。 
    
- 对于非重复元素（即 **MaxOccurs** 为"1"的元素），会将源元素的属性添加到目标元素的现有属性。 
    
## <a name="creating-a-custom-transform"></a>创建自定义转换

合并表单时的默认操作非常适合于基于相同 XML 架构的表单。但是，在某些情况下，您可能需要合并基于不同架构的表单，或者为基于相同架构的表单覆盖默认合并操作。对于这些方案，您可以创建一个 XSL 转换 (XSLT)，其中包含用于合并操作的聚合指令。将在合并时应用该转换，以创建一个 DOM 文档，该文档包含要导入的信息，以及指定如何将此信息并入目标文档的注释。这些注释是命名空间  `https://schemas.microsoft.com/office/InfoPath/2003/aggregation` 中的 XML 属性。
  
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

结合  `https://schemas.microsoft.com/office/InfoPath/2003/aggregation` 命名空间中指定的属性，可以使用  `https://schemas.microsoft.com/office/infopath/2003/aggregation-target` 命名空间来指示实现接口 **IXMLDOMDocument** 的 XSL 对象。此接口最有用的成员之一是方法 **get-documentElement**。
  
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
    
2. 为现有 InfoPath 表单的每种 XML 源文档派生 XML 模式。 通过使用 Backstage 的“发布”**** 选项卡上的“导出源文件”**** 命令导出 XML 架构，可以轻松完成此步骤。 对于不是在 InfoPath 中创建的 XML 文档，可以使用 Microsoft Visual Studio 等工具从示例 XML 文档创建架构，也可以从 InfoPath 中的 XML 文档创建示例表单，然后导出 InfoPath 从文档结构派生出来的架构。 
    
3. 确定要从每种 XML 源文档中合并的数据。此步骤将几乎完全取决于源表单和目标表单的要求。对于某些表单，您可能需要从源表单中复制所有数据。对于其他表单，则可能只需要从表单的基础 XML 文档中复制一两个元素。在确定要合并什么数据时，要格外留意源文档和目标文档，以确保元素在两个表单之间有逻辑地映射。
    
4. 为每种 XML 源文档创建 XSL 转换。在配置表单的合并时，此步骤将花费大部分时间。XSL 转换的目的是将源 XML 文档转换为可与目标表单合并的格式。在设计转换时，要决定是要使用通过 XML 位置路径进行的合并，还是使用通过 InfoPath 聚合指令进行的合并。
    
    利用 Visual Studio 工具可以方便地创建 XSL 转换。Visual Studio 提供了语法颜色设置和文档大纲。它还能自动为 XSL 元素提供结束标记，从而可帮助减少冗长的键入和难于查找的拼写错误。也可以使用诸如记事本等文本编辑器来创建 XSL 转换。
    
    首先创建标识转换，该转换仅仅是一个输出相同 XSL 文件（作为输入）的 XSL 转换：
    
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

    然后，为要增加特殊处理的元素添加替代模板节。例如，此模板将  `<src:Task>` 元素更改为  `<my:field1>` 元素，并将 **agg:action** 属性的值设置为"replace"。 
    
    ```XML
        <xsl:template match="src:Task"> 
            <my:field1 agg:select="/my:myFields/my:field1" agg:action="replace"> 
                <xsl:value-of select="."/> 
            </my:field1> 
        </xsl:template>
    ```

5. 在表单模板中添加 XSL 转换文件和架构文件。 为每种源文档派生架构并创建 XSL 转换以转换每种文档类型以便 InfoPath 可以合并其数据后，将它们作为资源添加到表单中。 单击“数据”**** 选项卡上的“资源文件”****，然后单击“资源文件”**** 对话框中的“添加”****，浏览到你的架构或 XSL 转换文件，然后单击“确定”****。 对创建的每个架构文件和 XSL 转换文件执行此操作。
    
    如果所添加的架构使用 **targetNamespace** 属性，则必须将一个属性元素添加到表单的 .xsf 文件中，以便 InfoPath 知道架构的命名空间。 若要访问此文件，请单击“文件”**** 选项卡，单击“发布”****，然后单击“导出源文件”****。 选择文件的位置，然后单击“确定”****。 然后关闭你正在设计的 InfoPath 表单模板。
    
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

在托管代码中，可以通过选中“使用自定义代码合并”**** 框，然后单击 Backstage 中“表单选项”**** 对话框的“高级”**** 类别中的“编辑”**** 按钮来启用 [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) 事件。 
  

