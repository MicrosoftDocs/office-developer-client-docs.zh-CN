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

SETF ( GETREF (** *cell* ** ) ， ** *formula* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cell_ <br/> |必需  <br/> |**String** <br/> |要设置其公式的单元格。  <br/> |
| _formula_ <br/> |必需  <br/> |**String** <br/> |要使用的公式。  <br/> |
   
## <a name="remarks"></a>备注

计算时，formula 中的表达式  _结果将成为单元格_ 中的新  _公式_。 如果  _formula_ 括在引号中，则引用的表达式将写入  _单元格_。 若要将  _单元格_ 设置为字符串，请用三组引号将  _公式_ 括起来。 
  
目标单元格必须使用 GETREF() 引用来指定或必须指定为一个字符串，以避免循环。最好使用 GETREF，因为 Microsoft Visio 能够在形状移到不同的文档时调整引用。
  
如果没有  _使用_ GETREF 或字符串指定单元格，函数将返回错误，并且单元格的公式不变。 如果  _formula_ 包含语法错误，函数将返回错误，并且  _单元格中的公式_ 不会更改。 
  
## <a name="example-1"></a>示例 1

SETF ( GETREF (Scratch.A1) ， 1.5 in \* 6 + 1 ft) 
  
将 Scratch.A1 的公式设置为 21 英寸。
  
## <a name="example-2"></a>示例 2

SETF ( GETREF (Scratch.A1) ，"1.5 in \* 6 + 1 ft") 
  
将 Scratch. A1 到表达式 1.5 in \* 6+1 ft。
  
## <a name="example-3"></a>示例 3

SETF( GETREF(Scratch.A1), """Say """"ahh""""""")
  
将 Scratch.A1 的公式设置为字符串“Say ""ahh""”，该字符串相当于“Say "ahh"”。
  

