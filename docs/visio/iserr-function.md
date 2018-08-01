---
title: ISERR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251448
localization_priority: Normal
ms.assetid: 87508007-8ad2-3bcf-55dc-f0207c7c6fe3
description: '将返回 TRUE 如果 cellreference 的值是任何错误类型除外 # n/A;否则，将返回 FALSE。 ISERR 函数可以用于引用另一个单元格的公式。'
ms.openlocfilehash: 651b095e53b7f2690aa9c8774d87d5afcede75be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780475"
---
# <a name="iserr-function"></a>ISERR 函数

返回_cellreference_的值为任何错误类型时为 TRUE 除外 # n/A;否则，将返回 FALSE。 ISERR 函数可以用于引用另一个单元格的公式。 
  
## <a name="syntax"></a>语法

ISERR (* * *cellreference* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellreference_ <br/> |必需  <br/> |**字符串** <br/> |对单元格的引用。  <br/> |
   
## <a name="example-1"></a>示例 1

|**Cell**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.A1  <br/> |=NA( )  <br/> |#N/A!  <br/> |
|Scratch.B1  <br/> |=ISERR(Scratch.A1)  <br/> |FALSE  <br/> |
   
返回 FALSE，因为 ISERR 函数不能识别 #N/A! 错误。使用 ISERROR 可查找所有错误类型。
  
## <a name="example-2"></a>示例 2

|**Cell**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.X1  <br/> |="House"  <br/> |#VALUE!  <br/> |
|Scratch.A1  <br/> |=ISERR(Scratch.X1)  <br/> |TRUE  <br/> |
   
返回 TRUE，因为 ISERR 函数可以识别 #VALUE! 错误。
  

