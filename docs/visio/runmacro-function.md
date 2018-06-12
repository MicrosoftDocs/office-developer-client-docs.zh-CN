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
description: 调用宏在 Microsoft Visual Basic for Applications (VBA) 项目。
ms.openlocfilehash: e3dd989956ce9c5f795ae3ef0d8535ab2776d6d7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781209"
---
# <a name="runmacro-function"></a>RUNMACRO 函数

调用宏在 Microsoft Visual Basic for Applications (VBA) 项目。 
  
## <a name="syntax"></a>语法

RUNMACRO (* * *macroname* * * [，* * *projname_opt* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _macroname_ <br/> |必需  <br/> |**字符串** <br/> |要调用的宏的名称。  <br/> |
| _projname_opt_ <br/> |可选  <br/> |**字符串** <br/> | 包含宏的项目。  <br/> |
   
## <a name="remarks"></a>注解

如果指定一个项目，则 Microsoft Visio 将扫描一个包含_projname_opt_和呼叫_macroname_该项目中的所有打开的文档。 如果_projname_opt_被省略或 null ("")，则假定_macroname_可在 VBA 项目中的文档的包含 RUNMACRO 公式进行计算。 
  
RUNMACRO 函数与 CALLTHIS 函数不同，不传递到拥有对_macroname_计算的公式的形状的引用。 CALLTHIS，如 RUNMACRO 函数不需要对_projname_opt_调用它的引用。 
  
 在 Visio 实例对公式中的 RUNMACRO 函数求值时所调用的 VBA 代码不应关闭包含使用该函数的单元格的文档，因为这样会导致应用程序出错，并且 Visio 将终止。 
  
如果您需要关闭包含使用 RUNMACRO 函数的单元格的文档，则请使用下列方法之一：
  
- 从非 VBA 的代码关闭文档。
    
- 从正在关闭的项目之外的其他项目关闭文档。
    
- 将关闭窗口的窗口消息张贴到文档中，而不是关闭该文档。
    
有关在 Visio 中运行代码的详细信息，请参阅[关于安全设置和运行代码在 Visio](about-security-settings-and-running-code-in-visio-shapesheet.md) ShapeSheet 参考中。 
  
## <a name="example"></a>示例

下面的示例调用包含 RUNMACRO 公式的 VBA 项目的 ThisDocument 类模块中名为 MyTest 的宏。 
  
RUNMACRO ("ThisDocument.MyTest") 
  

