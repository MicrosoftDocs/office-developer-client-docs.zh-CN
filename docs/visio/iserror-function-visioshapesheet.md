---
title: ISERROR 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251452
localization_priority: Normal
ms.assetid: 4864ebc2-fee6-2415-7c59-e0af8611f8d6
description: 如果 cellreference 的值为任何错误类型，则返回 TRUE;否则，它将返回 FALSE。 ISERROR 函数用于引用另一个单元格的公式。
ms.openlocfilehash: a07b2345858e36dc2e4514d7e4f0f0d653491b50
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421541"
---
# <a name="iserror-function-visioshapesheet"></a>ISERROR 函数 (VisioShapeSheet)

如果  _cellreference_ 的值为任何错误类型，则返回 TRUE;否则，它将返回 FALSE。 ISERROR 函数用于引用另一个单元格的公式。 
  
## <a name="syntax"></a>语法

ISERROR (** *cellreference* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellreference_ <br/> |必需  <br/> |**String** <br/> |对单元格的引用。  <br/> |
   
## <a name="example-1"></a>示例 1

|**Cell**|**公式**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.A1  <br/> |=NA( )  <br/> |#N/A！  <br/> |
|Scratch.B1  <br/> |=ISERROR (Scratch.A1)   <br/> |TRUE  <br/> |
   
返回 TRUE，因为 ISERROR 函数可以识别 #N/A! 错误。您可以使用 ISERR 查找除 #N/A! 错误之外的所有错误类型。
  
## <a name="example-2"></a>示例 2

|**Cell**|**公式**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.X1  <br/> |="House"  <br/> |#VALUE!  <br/> |
|Scratch.B1  <br/> |=ISERROR (Scratch.X1)   <br/> |TRUE  <br/> |
   
返回 TRUE，因为 ISERROR 函数可以识别 #VALUE! 错误。若要基于 #VALUE! 错误生成一个表达式，请使用 ISERRVALUE 函数。
  

