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
description: '如果 cellreference 的值是除 #N/A 之外的任何错误类型，则#N TRUE;否则，它将返回 FALSE。 ISERR 函数用于引用另一个单元格的公式。'
ms.openlocfilehash: e2117c38d3cad2408295ed6894aefc78e107596e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432105"
---
# <a name="iserr-function"></a>ISERR 函数

如果  _cellreference_ 的值是除 #N/A 之外的任何错误类型，则#N TRUE;否则，它将返回 FALSE。 ISERR 函数用于引用另一个单元格的公式。 
  
## <a name="syntax"></a>语法

ISERR (** *cellreference* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellreference_ <br/> |必需  <br/> |**String** <br/> |对单元格的引用。  <br/> |
   
## <a name="example-1"></a>示例 1

|**Cell**|**公式**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.A1  <br/> |=NA( )  <br/> |#N/A！  <br/> |
|Scratch.B1  <br/> |=ISERR (Scratch.A1)   <br/> |FALSE  <br/> |
   
返回 FALSE，因为 ISERR 函数不能识别 #N/A! 错误。使用 ISERROR 可查找所有错误类型。
  
## <a name="example-2"></a>示例 2

|**Cell**|**公式**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.X1  <br/> |="House"  <br/> |#VALUE!  <br/> |
|Scratch.A1  <br/> |=ISERR (Scratch.X1)   <br/> |TRUE  <br/> |
   
返回 TRUE，因为 ISERR 函数可以识别 #VALUE! 错误。
  

