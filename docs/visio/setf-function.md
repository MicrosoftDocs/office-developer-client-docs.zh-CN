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
ms.openlocfilehash: a1e6a12014a77a20c0968b3ed2f7bc25badad8ce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781242"
---
# <a name="setf-function"></a>SETF 函数

设置单元格的公式。 
  
## <a name="syntax"></a>语法

SETF (GETREF (* **单元格** *)，* **公式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _单元格_ <br/> |必需  <br/> |**字符串** <br/> |单元格要设置其公式。  <br/> |
| _formula_ <br/> |必需  <br/> |**字符串** <br/> |要使用的公式。  <br/> |
   
## <a name="remarks"></a>注解

在计算时，在_公式_表达式的结果将成为_单元_格中的新公式。 如果_公式_括在引号内，则引用的表达式写入_单元格_。 将_单元格_设置为一个字符串，将括在引号三组的_公式_。 
  
目标单元格必须使用 GETREF() 引用来指定或必须指定为一个字符串，以避免循环。最好使用 GETREF，因为 Microsoft Visio 能够在形状移到不同的文档时调整引用。
  
如果未使用 GETREF 指定_单元格_或为 string，函数将返回错误，并且更改任何单元格的公式。 如果_公式_包含语法错误，函数将返回错误，并且不更改_单元_格中的公式。 
  
## <a name="example-1"></a>示例 1

SETF (GETREF(Scratch.A1)，1.5 中\*6 + 1 ft)
  
将 Scratch.A1 的公式设置为 21 英寸。
  
## <a name="example-2"></a>示例 2

SETF (GETREF(Scratch.A1)，"中的 1.5 \* 6 + 1 ft")
  
设置挑战的公式。 对表达式 1.5 中 A1\*6 + 1 英尺。
  
## <a name="example-3"></a>示例 3

SETF( GETREF(Scratch.A1), """Say """"ahh""""""")
  
将 Scratch.A1 的公式设置为字符串“Say ""ahh""”，该字符串相当于“Say "ahh"”。
  

