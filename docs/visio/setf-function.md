---
title: SETF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251496
localization_priority: Normal
ms.assetid: fcf415c1-171f-b75f-6e40-2bbdbe8b1cfb
description: 设置单元格的公式。
ms.openlocfilehash: 63050de92394ebbdce6cfe053e15347ca3ce5c7f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425972"
---
# <a name="setf-function"></a>SETF 函数

设置单元格的公式。 
  
## <a name="syntax"></a>语法

SETF (GETREF (* * *cell* * *), * * *formula* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _单元_ <br/> |必需  <br/> |**String** <br/> |要设置其公式的单元格。  <br/> |
| _formula_ <br/> |必需  <br/> |**String** <br/> |要使用的公式。  <br/> |
   
## <a name="remarks"></a>说明

当计算时, _formula_中表达式的结果将成为_单元格中_的新公式。 如果将_formula_括在引号中, 则会将引用的表达式写入_单元格_。 若要将_单元格_设置为字符串, 请将_公式_括在三个引号中。 
  
目标单元格必须使用 GETREF() 引用来指定或必须指定为一个字符串，以避免循环。最好使用 GETREF，因为 Microsoft Visio 能够在形状移到不同的文档时调整引用。
  
如果_单元格_不是使用 GETREF 或字符串指定的, 则函数将返回错误, 并且不会更改单元格的公式。 如果_公式_中包含语法错误, 函数将返回错误, 并且_单元格中_的公式不会更改。 
  
## <a name="example-1"></a>示例 1

SETF (GETREF (1.5), 6 + 1 英尺\*中的
  
将 Scratch.A1 的公式设置为 21 英寸。
  
## <a name="example-2"></a>示例 2

SETF (GETREF (), "1.5 \* 6 英尺1英尺")
  
将 Scratch. A1 到\*6 + 1 英尺的表达式1.5。
  
## <a name="example-3"></a>示例 3

SETF( GETREF(Scratch.A1), """Say """"ahh""""""")
  
将 Scratch.A1 的公式设置为字符串“Say ""ahh""”，该字符串相当于“Say "ahh"”。
  

