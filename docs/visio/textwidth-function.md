---
title: TEXTWIDTH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251505
localization_priority: Normal
ms.assetid: a9b8efcf-edc0-ad99-deae-21df16c58807
description: 返回形状中的撰写文本的宽度。
ms.openlocfilehash: d96b9489c08ce38205f8e9ad91e361fcb643c39c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781496"
---
# <a name="textwidth-function"></a>TEXTWIDTH 函数

返回形状中的撰写文本的宽度。 
  
## <a name="syntax"></a>语法

TEXTWIDTH (* * *shapename ！TheText* * * * * *[，最大宽度]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _shapename ！ theText_ <br/> |必需  <br/> |**字符串** <br/> |单元格的引用的目标形状中名为 TheText。  _shapename ！_ 是要从中检索文本的名称。  <br/> |
| _最大宽度_ <br/> |可选  <br/> |**Numeric** <br/> |文本块的最大宽度。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

TEXTWIDTH 函数常用于调整形状的宽度，以适合它所包含的文本。
  
如果_sheetN ！_ 被省略，默认形状为当前形状。 
  
如果指定_最大宽度_，则结果是文本的最长的_最大宽度_相适应行。 如果省略_最大宽度_，则结果为文本的总宽度。 
  
## <a name="example"></a>示例

TEXTWIDTH(TheText) 
  
返回当前形状中文本的总长度。 
  

