---
title: DOOLEVERB 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251421
localization_priority: Normal
ms.assetid: d276c122-6326-75a7-220c-6a78e94e0db0
description: 执行 OLE 对象的动作。
ms.openlocfilehash: c339d03a00afdf7f777bb0624ddb8fa75f277e05
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301489"
---
# <a name="dooleverb-function"></a>DOOLEVERB 函数

执行 OLE 对象的动作。
  
## <a name="syntax"></a>语法

DOOLEVERB ("* * *verb* * *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _动词_ <br/> |必需  <br/> |**String** <br/> |要执行的动作。  <br/> |
   
## <a name="remarks"></a>注解

在 Visio 的早期版本中，此函数以 _DOOLEVERB 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。 
  
## <a name="example"></a>示例

DOOLEVERB ("edit")
  
运行 OLE 对象程序，并显示链接或嵌入的对象，以便进行编辑。
  

