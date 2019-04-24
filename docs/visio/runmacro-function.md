---
title: RUNMACRO 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033809
localization_priority: Normal
ms.assetid: 86b0f071-5e0b-56de-ff5b-63c114ad823a
description: 调用 Microsoft Visual Basic for Applications (VBA) 项目中的宏。
ms.openlocfilehash: 77045bd67fe9be9aab14e73199b33b93c6d70c2c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355711"
---
# <a name="runmacro-function"></a>RUNMACRO 函数

调用 Microsoft Visual Basic for Applications (VBA) 项目中的宏。 
  
## <a name="syntax"></a>语法

RUNMACRO (* * *macroname* * * [, * * *projname_opt* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _macroname_ <br/> |必需  <br/> |**String** <br/> |要调用的宏的名称。  <br/> |
| _projname_opt_ <br/> |可选  <br/> |**字符串** <br/> | 包含宏的项目。  <br/> |
   
## <a name="remarks"></a>注解

如果指定了一个项目, Microsoft Visio 将扫描所有打开的文档, 其中包含_projname_opt_并调用该项目中的_macroname_ 。 如果_projname_opt_被省略或为空 (""), 则假定_macroname_在包含所评估的 RUNMACRO 公式的文档的 VBA 项目中。 
  
RUNMACRO 函数与 CALLTHIS 函数的不同之处在于, 它不会传递对将计算结果为_macroname_的公式的形状的引用。 与 CALLTHIS 一样, RUNMACRO 函数不需要对_projname_opt_的引用即可对其进行调用。 
  
 在 Visio 实例对公式中的 RUNMACRO 函数求值时所调用的 VBA 代码不应关闭包含使用该函数的单元格的文档，因为这样会导致应用程序出错，并且 Visio 将终止。 
  
如果您需要关闭包含使用 RUNMACRO 函数的单元格的文档，则请使用下列方法之一：
  
- 从非 VBA 的代码关闭文档。
    
- 从正在关闭的项目之外的其他项目关闭文档。
    
- 将关闭窗口的窗口消息张贴到文档中，而不是关闭该文档。
    
有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。 
  
## <a name="example"></a>示例

下面的示例调用包含 RUNMACRO 公式的 VBA 项目的 ThisDocument 类模块中名为 MyTest 的宏。 
  
RUNMACRO ("ThisDocument.MyTest") 
  

