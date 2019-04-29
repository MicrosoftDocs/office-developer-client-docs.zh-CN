---
title: SHAPETEXT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251788
localization_priority: Normal
ms.assetid: 87ea5e8f-c3e0-009f-4bf8-8c34fbdb83a6
description: 从形状中获取文本。
ms.openlocfilehash: bb9b1fbe5900cd051828ed6c7ff07546567c1b23
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419343"
---
# <a name="shapetext-function"></a>SHAPETEXT 函数

从形状中获取文本。 
  
## <a name="syntax"></a>语法

SHAPETEXT (* * *shapename!TheText* * * * * *[, 标志]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _shapename!TheText_ <br/> |必需  <br/> ||对目标形状中名为 TheText 的单元格的引用。  _Shapename!_ 是要从中检索文本的形状的名称。  <br/> |
| _flag_ <br/> |可选  <br/> |**数值** <br/> |指定文本格式的位。 默认标志 (0) 显示的文本与形状中显示的文本完全相同。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>说明

您可以将下列任意标志组合与 SHAPETEXT 函数一起使用。
  
|**Flag**|**说明**|
|:-----|:-----|
|0  <br/> |显示的文本与形状中显示的文本完全相同。  <br/> |
|1  <br/> |包括任意连字符。  <br/> |
|双面  <br/> |不包括域中的扩展文本。  <br/> |
|4  <br/> |将制表符转换为一个空格。  <br/> |
|utf-8  <br/> |将制表符转换为一组空格。  <br/> |
|16   <br/> |将回车符和换行符转换为空格。  <br/> |
|32  <br/> |将版式双引号转换为常规双引号。  <br/> |
|64  <br/> |将相邻空白区域转换为单个空格。  <br/> |
   
## <a name="example-1"></a>示例 1

SHAPETEXT (sheetN! theText)
  
返回名为 sheetN 的形状的文本，与在形状中显示的文本完全相同。
  
## <a name="example-2"></a>示例 2

SHAPETEXT (theText)
  
返回当前形状的文本，与在形状中显示的文本完全相同。
  
## <a name="example-3"></a>示例 3

SHAPETEXT(theText, 84)
  
返回当前形状的文本。另外还将相邻空白区域转换为单个空格 (64)、将回车符和换行符转换为空格 (16)，并将制表符转换为单个空格 (4)。这些标志的总和为 84。
  

