---
title: 在 InfoPath 表单模板中使用自定义 XSLT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 32c80bcd-a5d6-af32-38ba-9ca9ff148b99
description: 您可以在 Microsoft InfoPath 表单设计器中创建可能会需要的大多数视图元素。但是，如果需要 InfoPath 无法创建的自定义视图元素，则可以手动修改 InfoPath 用于生成视图的 XSL 转换 (XSLT)。为此，请使用 Microsoft Office Backstage 的发布选项卡上的导出源文件，将表单提取到其组件文件中，然后在首选的 XML 编辑器（如 Microsoft Visual Studio 或记事本）中编辑转换。
ms.openlocfilehash: a61980191dbedeec33b06ad8173ce50126fea781
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428268"
---
# <a name="using-custom-xslt-in-infopath-form-templates"></a>在 InfoPath 表单模板中使用自定义 XSLT

You can create most of the view elements you're likely to need in the Microsoft InfoPath form designer. If you need a custom view element that InfoPath can't create for you, however, you can manually modify the XSL Transformation (XSLT) that InfoPath uses to generate the view. To do so, extract the form into its component files by using **Export Source Files** on the **Publish** tab of the Microsoft Office Backstage, and then edit the transform in your preferred XML editor, such as Microsoft Visual Studio or Notepad. 
  
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

Elements and constructs defined within XSL templates with the  `xd:preserve` mode will not be displayed in the InfoPath design environment. Instead, InfoPath will mark the custom section with a control labeled **Preserve Code Block** with a red border. When a user opens the form to fill it out, the custom XSL transforms are applied and the **Preserve Code Block** controls will not appear. 
  

