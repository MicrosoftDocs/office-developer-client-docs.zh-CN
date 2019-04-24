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
description: 返回形状中撰写的文本的宽度。
ms.openlocfilehash: 43848bba4d24a0c31a3a084d123cd56140bf0709
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332268"
---
# <a name="textwidth-function"></a>TEXTWIDTH 函数

返回形状中撰写的文本的宽度。 
  
## <a name="syntax"></a>语法

TEXTWIDTH (* * *shapename!TheText* * * * * *[, maximumwidth]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _shapename! theText_ <br/> |必需  <br/> |**String** <br/> |对目标形状中名为 TheText 的单元格的引用。  _shapename!_ 是要从中检索文本的形状的名称。  <br/> |
| _maximumwidth_ <br/> |可选  <br/> |**Numeric** <br/> |文本块的最大宽度。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

TEXTWIDTH 函数常用于调整形状的宽度，以适合它所包含的文本。
  
如果_sheetN!_ 被省略, 则默认形状为当前形状。 
  
如果指定了_maximumwidth_ , 则结果是适合在_maximumwidth_中的文本的最长行。 如果省略_maximumwidth_ , 则结果为文本的总宽度。 
  
## <a name="example"></a>示例

TEXTWIDTH (TheText) 
  
返回当前形状中文本的总长度。 
  

