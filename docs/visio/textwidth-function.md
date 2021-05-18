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
description: 返回形状中组合文字的宽度。
ms.openlocfilehash: 43848bba4d24a0c31a3a084d123cd56140bf0709
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422031"
---
# <a name="textwidth-function"></a>TEXTWIDTH 函数

返回形状中组合文字的宽度。 
  
## <a name="syntax"></a>语法

TEXTWIDTH (** *shapename！TheText* ** ** *[，maximumwidth]* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _shapename！theText_ <br/> |必需  <br/> |**String** <br/> |对目标形状中名为 TheText 的单元格的引用。  _shapename！_ 是想要从中检索文本的形状的名称。  <br/> |
| _maximumwidth_ <br/> |可选  <br/> |**Numeric** <br/> |文本块的最大宽度。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>备注

TEXTWIDTH 函数常用于调整形状的宽度，以适合它所包含的文本。
  
如果  _sheetN！_ 省略，默认形状是当前形状。 
  
如果  _指定了 maximumwidth，_ 则结果是适合  _maximumwidth_ 的最长文本行。 如果  _省略 maximumwidth，_ 则结果是文本的总宽度。 
  
## <a name="example"></a>示例

TEXTWIDTH (Text)  
  
返回当前形状中文本的总长度。 
  

