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
ms.openlocfilehash: 017dd89bd3b814c10422cd32eea1ee7e343eaf50
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417194"
---
# <a name="ang360-function"></a>ANG360 函数

将角度\<的范围规范化为 0 = result \< 2PI 弧度 (0 \<= 结果\< 360 度)。
  
## <a name="syntax"></a>语法

ANG360 (* * *angle* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _angle_ <br/> |必需  <br/> |**数值** <br/> |待规范化的角度。  <br/> |
   
## <a name="remarks"></a>说明

如果不使用角度单位指定*angle* , 则将其解释为弧度。 如果*angle*无法转换为值, #VALUE! 错误。 
  
## <a name="example-1"></a>示例 1

ANG360(395 deg)
  
返回 35 度
  
## <a name="example-2"></a>示例 2

ANG360(-9.8 rad)
  
返回 2.7664 弧度
  
## <a name="example-3"></a>示例 3

ANG360 (45)
  
返回 58.31 度（1.0177 弧度）
  

