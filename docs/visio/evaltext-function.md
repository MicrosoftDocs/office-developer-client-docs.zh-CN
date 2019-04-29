---
title: EVALTEXT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251422
localization_priority: Normal
ms.assetid: c9b5b96c-d8c8-6119-e3f1-a2ce9d7c043e
description: 评估 shapename 中的文本, 就好像它是一个公式并返回结果。
ms.openlocfilehash: 6600d9d6ddaf630a93fdb5c37639ce50a21a4307
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438356"
---
# <a name="evaltext-function"></a>EVALTEXT 函数

评估_shapename_中的文本, 就好像它是一个公式并返回结果。 
  
## <a name="syntax"></a>语法

EVALTEXT (* * *shapename! theText* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _shapename! theText_ <br/> |必需  <br/> |**String** <br/> |当关联形状的文本构成改变时触发的单元格。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>说明

 _shapename_ 可用来指代某形状（不是当前形状）的文本。 
  
如果没有文本，则结果为零。 如果无法对文本求值，则该函数将返回错误。
  
## <a name="example"></a>示例

EVALTEXT (第2行! theText) 
  
对形状 Line.2 中包含的文本求值。例如，如果 Line.2 包含“4 ft + 0.5 ft”，则返回的值为 4.5 ft。 
  

