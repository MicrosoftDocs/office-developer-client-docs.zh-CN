---
title: TEXTHEIGHT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251504
localization_priority: Normal
ms.assetid: 5a10892f-c8fa-c127-2f5a-564009ce5411
description: 返回组合的文本的高度形状中没有文本行其中超过最大宽度。
ms.openlocfilehash: 9a80dafcf80a1dcba968a0f60465aae4e2a2758b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781498"
---
# <a name="textheight-function"></a>TEXTHEIGHT 函数

返回组合的文本的高度形状中没有文本行其中超过_最大宽度_。 
  
## <a name="syntax"></a>语法

TEXTHEIGHT (* * *shapename ！TheText* * * * * *[，最大宽度]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _shapename ！ theText_ <br/> |必需  <br/> |**字符串** <br/> |单元格的引用的目标形状中名为 TheText。  _shapename ！_ 是要从中检索文本的名称。  <br/> |
| _最大宽度_ <br/> |可选  <br/> |**Numeric** <br/> |文本块的最大宽度。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

返回的值包括文本高度，其中包括文本前后的空格、文本的行间距和上下文本块边距。此函数常用于调整形状的高度，以适合它所包含的文本。
  
## <a name="example"></a>示例

TEXTHEIGHT(TheText,(Width - 0.5 in)) 
  
返回当文本按形状宽度减去 0.5 英寸后的宽度折行时文本的高度。 
  

