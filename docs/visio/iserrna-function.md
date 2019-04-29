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
description: '如果 cellreference 的值为错误类型 #N/a!, 则返回 TRUE。 (不可用);否则, 它将返回 FALSE。 ISERRNA 函数在引用其他单元格的公式中使用。'
ms.openlocfilehash: 8a398eca6da659a6b8f29e4ef8e31b18abf56fde
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432112"
---
# <a name="iserrna-function"></a>ISERRNA 函数

如果_cellreference_的值为错误类型 #N/a!, 则返回 TRUE。 (不可用);否则, 它将返回 FALSE。 ISERRNA 函数在引用其他单元格的公式中使用。 
  
## <a name="syntax"></a>语法

ISERRNA (* * *cellreference* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellreference_ <br/> |必需  <br/> |**String** <br/> |对单元格的引用。  <br/> |
   
## <a name="example-1"></a>示例 1

|**单元格**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|草稿。 A1  <br/> |="5 + 3"  <br/> |utf-8  <br/> |
|草稿 B1  <br/> |= ISERRNA (的 A1)  <br/> |FALSE  <br/> |
   
返回 FALSE，因为返回的值可用。
  
## <a name="example-2"></a>示例 2

|**单元格**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|草稿。 A1  <br/> |=NA( )  <br/> |#N/A!  <br/> |
|草稿 B1  <br/> |= ISERRNA (的 A1)  <br/> |TRUE  <br/> |
   
返回 TRUE，因为返回的值是 #N/A! 错误类型。
  

