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
ms.openlocfilehash: 7a16a77a990180f34dd7a5706c24ec3232438467
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439896"
---
# <a name="floor-function"></a>FLOOR 函数

将数字向 0 (零) 舍入为下一个整数或下一个实例的_倍数_。
  
## <a name="syntax"></a>语法

基底 (* **数字** *、* **多** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Number** <br/> |要舍入的数字。  <br/> |
| _多位_ <br/> |必需  <br/> |**Number** <br/> |要舍入到的倍数。  <br/> |
   
### <a name="return-value"></a>返回值

数字
  
## <a name="remarks"></a>说明

如果未指定_多个_, 则数字将向0舍入到下一个整数。 
  
 _数字_和_多个_必须具有相同的符号或 #NUM! 错误。 如果_number_或_倍数_无法转换为值, #VALUE! 错误。 如果有一个_数_或_多个_值为 0, 则结果为0。 
  
## <a name="example-1"></a>示例 1

基底 (3.7)
  
返回 3。
  
## <a name="example-2"></a>示例 2

基底 (-3.7)
  
返回 -3。
  
## <a name="example-3"></a>示例 3

基底 (3.7, 0.5)
  
返回 3.5。
  

