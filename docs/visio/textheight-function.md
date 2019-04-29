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
description: 返回组合文本的高度, 该形状中的文本行数超过 maximumwidth。
ms.openlocfilehash: 7455f58f14f9a4a0ae1fcd5375dba5d5860d3852
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427407"
---
# <a name="textheight-function"></a>TEXTHEIGHT 函数

返回组合文本的高度, 该形状中的文本行数超过_maximumwidth_。 
  
## <a name="syntax"></a>语法

TEXTHEIGHT (* * *shapename!TheText* * * * * *[, maximumwidth]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _shapename! theText_ <br/> |必需  <br/> |**String** <br/> |对目标形状中名为 TheText 的单元格的引用。  _shapename!_ 是要从中检索文本的形状的名称。  <br/> |
| _maximumwidth_ <br/> |可选  <br/> |**数值** <br/> |文本块的最大宽度。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>说明

返回的值包括文本高度，其中包括文本前后的空格、文本的行间距和上下文本块边距。此函数常用于调整形状的高度，以适合它所包含的文本。
  
## <a name="example"></a>示例

TEXTHEIGHT(TheText,(Width - 0.5 in)) 
  
返回当文本按形状宽度减去 0.5 英寸后的宽度折行时文本的高度。 
  

