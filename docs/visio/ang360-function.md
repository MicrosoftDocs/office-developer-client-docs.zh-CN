---
title: ANG360 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251392
localization_priority: Normal
ms.assetid: 23e6899d-0a94-a7d8-8de2-091e0531f163
description: 规范化角度的范围。
ms.openlocfilehash: 6916e50daad735843bf0a2a6361fb5b1b833e2ce
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160298"
---
# <a name="ang360-function"></a>ANG360 函数

将角度的范围规范化为 0 = 结果 \< \< 2PI 弧度， (0 = 结果 \< \< 360 度) 。
  
## <a name="syntax"></a>语法

ANG360 (***角度*** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _angle_ <br/> |必需  <br/> |**Numeric** <br/> |待规范化的角度。  <br/> |
   
## <a name="remarks"></a>备注

如果没有  *使用*  角度单位指定 angle，则将其解释为弧度。 如果  *angle*  无法转换为值，#VALUE！ 错误。 
  
## <a name="example-1"></a>示例 1

ANG360(395 deg)
  
返回 35 度
  
## <a name="example-2"></a>示例 2

ANG360(-9.8 rad)
  
返回 2.7664 弧度
  
## <a name="example-3"></a>示例 3

ANG360 (45) 
  
返回 58.31 度（1.0177 弧度）
  

