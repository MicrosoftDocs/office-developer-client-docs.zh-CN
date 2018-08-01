---
title: ISERROR Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251452
localization_priority: Normal
ms.assetid: 4864ebc2-fee6-2415-7c59-e0af8611f8d6
description: 返回 TRUE 的 cellreference 值是否任何错误类型;否则，将返回 FALSE。 引用另一个单元格的公式中使用 ISERROR 函数。
ms.openlocfilehash: c93801f5d61e45be5d178027405ead3aa129654d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780489"
---
# <a name="iserror-function-visioshapesheet"></a>ISERROR Function (VisioShapeSheet)

返回 TRUE 的_cellreference_值是否任何错误类型;否则，将返回 FALSE。 引用另一个单元格的公式中使用 ISERROR 函数。 
  
## <a name="syntax"></a>语法

ISERROR (* * *cellreference* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellreference_ <br/> |必需  <br/> |**字符串** <br/> |对单元格的引用。  <br/> |
   
## <a name="example-1"></a>示例 1

|**Cell**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.A1  <br/> |=NA( )  <br/> |#N/A!  <br/> |
|Scratch.B1  <br/> |=ISERROR(Scratch.A1)  <br/> |TRUE  <br/> |
   
返回 TRUE，因为 ISERROR 函数可以识别 #N/A! 错误。您可以使用 ISERR 查找除 #N/A! 错误之外的所有错误类型。
  
## <a name="example-2"></a>示例 2

|**Cell**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.X1  <br/> |="House"  <br/> |#VALUE!  <br/> |
|Scratch.B1  <br/> |=ISERROR(Scratch.X1)  <br/> |TRUE  <br/> |
   
返回 TRUE，因为 ISERROR 函数可以识别 #VALUE! 错误。若要基于 #VALUE! 错误生成一个表达式，请使用 ISERRVALUE 函数。
  

