---
title: 在 InfoPath 表单模板中使用自定义 XSLT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 32c80bcd-a5d6-af32-38ba-9ca9ff148b99
description: 您可以在 Microsoft InfoPath 表单设计器中创建可能会需要的大多数视图元素。但是，如果需要 InfoPath 无法创建的自定义视图元素，则可以手动修改 InfoPath 用于生成视图的 XSL 转换 (XSLT)。为此，请使用 Microsoft Office Backstage 的发布选项卡上的导出源文件，将表单提取到其组件文件中，然后在首选的 XML 编辑器（如 Microsoft Visual Studio 或记事本）中编辑转换。
ms.openlocfilehash: 796115c99c81fc2a77812d91d317f5ce9ed54e5f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774093"
---
# <a name="using-custom-xslt-in-infopath-form-templates"></a>在 InfoPath 表单模板中使用自定义 XSLT

您可以在 Microsoft InfoPath 表单设计器中创建可能会需要的大多数视图元素。 但是，如果需要 InfoPath 无法创建的自定义视图元素，则可以手动修改 InfoPath 用于生成视图的 XSL 转换 (XSLT)。 为此，请使用 Microsoft Office Backstage 的“发布”**** 选项卡上的“导出源文件”****，将表单提取到其组件文件中，然后在首选的 XML 编辑器（如 Microsoft Visual Studio 或记事本）中编辑转换。 
  
如果在 InfoPath 外对视图转换进行更改，然后在设计模式中打开该视图并进行更改，InfoPath 将会覆盖您手动进行的更改。若要防止 InfoPath 覆盖您所做的更改，必须将这些更改放入转换中的  `<xsl:template>` 元素内，并使用  `xd:preserve` 模式，如下所示： 
  
```XML
<xsl:template match="my:field1" mode="xd:preserve"> 
   <div> 
      The value of field1 is <xsl:value-of select="."/> 
   </div> 
</xsl:template>
```

若要在转换文件中包含模板，请使用  `<xsl:apply-templates>` 元素以及同一  `xd:preserve` 模式： 
  
```XML
<xsl:apply-templates select="my:field1" mode="xd:preserve"/>
```

InfoPath 设计环境中不会显示使用 `xd:preserve` 模式在 XSL 模板中定义的元素和构造。 相反，InfoPath 将使用标记为带红框的**保留代码块**的控件标记自定义部分。 用户打开表单进行填写时，将应用自定义 XSL 转换，并且不会显示**保留代码块**控件。 
  

