---
title: ISERRNA 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251451
localization_priority: Normal
ms.assetid: 6ee7dc3d-efe9-c862-f71d-034b3d9c3ec6
description: '返回 TRUE，如果 cellreference 的值为错误类型 # n/A ！ （不可用）;否则，将返回 FALSE。 ISERRNA 函数引用另一个单元格的公式中使用。'
ms.openlocfilehash: a471119265d77866e51ccc6bb556f2ce0095d31d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780487"
---
# <a name="iserrna-function"></a>ISERRNA 函数

返回 TRUE，如果_cellreference_的值为错误类型 # n/A ！ （不可用）;否则，将返回 FALSE。 ISERRNA 函数引用另一个单元格的公式中使用。 
  
## <a name="syntax"></a>语法

ISERRNA (* * *cellreference* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellreference_ <br/> |必需  <br/> |**字符串** <br/> |对单元格的引用。  <br/> |
   
## <a name="example-1"></a>示例 1

|**Cell**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.A1  <br/> |="5 + 3"  <br/> |"8"  <br/> |
|Scratch.B1  <br/> |=ISERRNA(Scratch.A1)  <br/> |FALSE  <br/> |
   
返回 FALSE，因为返回的值可用。
  
## <a name="example-2"></a>示例 2

|**Cell**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.A1  <br/> |=NA( )  <br/> |#N/A!  <br/> |
|Scratch.B1  <br/> |=ISERRNA(Scratch.A1)  <br/> |TRUE  <br/> |
   
返回 TRUE，因为返回的值是 #N/A! 错误类型。
  

