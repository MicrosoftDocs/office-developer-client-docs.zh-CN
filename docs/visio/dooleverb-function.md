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
description: 执行动词 OLE 对象。
ms.openlocfilehash: a7786c3ef2b4039e288596ed367083a4ed3a6c13
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780130"
---
# <a name="dooleverb-function"></a>DOOLEVERB 函数

执行动词 OLE 对象。
  
## <a name="syntax"></a>语法

DOOLEVERB ("* **动词** *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _"动作"_ <br/> |必需  <br/> |**字符串** <br/> |要执行的动作。  <br/> |
   
## <a name="remarks"></a>注解

在 Visio 的早期版本中，此函数以 _DOOLEVERB 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。 
  
## <a name="example"></a>示例

DOOLEVERB("edit")
  
运行 OLE 对象程序，并显示链接或嵌入的对象，以便进行编辑。
  

