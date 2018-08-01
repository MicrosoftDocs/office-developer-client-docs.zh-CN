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
description: 规范化的角度的范围。
ms.openlocfilehash: 01092e06b55c73953417fe7d0fa1c9f74d668922
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779636"
---
# <a name="ang360-function"></a>ANG360 函数

规范化的角度范围为 0 \<= 结果\<2PI 弧度 (0 \<= 结果\<360 度)。
  
## <a name="syntax"></a>语法

ANG360 (* **角度** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _角度_ <br/> |必需  <br/> |**Numeric** <br/> |待规范化的角度。  <br/> |
   
## <a name="remarks"></a>注解

如果未使用角度单位指定*角度*，它被解释为弧度。 如果*angle*无法转换为一个值，#VALUE ！ 将返回错误。 
  
## <a name="example-1"></a>示例 1

ANG360(395 deg)
  
返回 35 度
  
## <a name="example-2"></a>示例 2

ANG360(-9.8 rad)
  
返回 2.7664 弧度
  
## <a name="example-3"></a>示例 3

ANG360(45)
  
返回 58.31 度（1.0177 弧度）
  

