---
title: FLOOR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251423
localization_priority: Normal
ms.assetid: 6788bc96-cc86-5f21-781f-67274e7f605a
description: 将数值向 0（零）舍入为下一个整数或 multiple 的下一个实例。
ms.openlocfilehash: f66b993e3ab48fd1abc685b7db5889d5bf24fbfc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780266"
---
# <a name="floor-function"></a>FLOOR 函数

舍入沿靠近 0 （零） 到下一个整数，或_多个_的下一个实例。
  
## <a name="syntax"></a>语法

FLOOR (* **数量** *，* **多个** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**编号** <br/> |要舍入的数值。  <br/> |
| _多个_ <br/> |必需  <br/> |**编号** <br/> |要舍入到的倍数。  <br/> |
   
### <a name="return-value"></a>返回值

Number
  
## <a name="remarks"></a>说明

如果未指定_multiple_ ，则数字将沿靠近 0 到下一个整数舍入。 
  
 _号码_和_多个_必须具有相同的迹象或 #NUM ！ 将返回错误。 如果_号码_或_多个_不能转换为一个值，#VALUE ！ 将返回错误。 如果_号码_或_多个_为 0，则结果为 0。 
  
## <a name="example-1"></a>示例 1

FLOOR(3.7)
  
返回 3。
  
## <a name="example-2"></a>示例 2

FLOOR(-3.7)
  
返回 -3。
  
## <a name="example-3"></a>示例 3

FLOOR(3.7, 0.5)
  
返回 3.5。
  

