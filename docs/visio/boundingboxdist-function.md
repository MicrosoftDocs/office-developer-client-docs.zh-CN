---
title: BOUNDINGBOXDIST 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8a2490f2-48c4-5df3-a3b3-40e8e0c80479
description: 返回形状边界框的指定部分的度量。
ms.openlocfilehash: 94cad37c4a0d2c6c7e7c69d997af09a9d7f1d651
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779802"
---
# <a name="boundingboxdist-function"></a>BOUNDINGBOXDIST 函数

返回形状边界框的指定部分的度量。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

BOUNDINGBOXDIST (* **索引** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _Index_ <br/> |必需  <br/> |**编号** <br/> |形状的一部分的边界框以测量并返回。 有关可能值，请参阅"说明"。  <br/> |
   
### <a name="return-value"></a>返回值

 **编号**
  
## <a name="remarks"></a>说明

 *Index*可为以下值之一。 
  
|**Item**|**值**|
|:-----|:-----|
|Width  <br/> |0  <br/> |
|Height  <br/> |1  <br/> |
|左边缘到形状的旋转中心点  <br/> |2  <br/> |
|形状的旋转中心点到右边缘  <br/> |3  <br/> |
|形状的旋转中心点到上边缘  <br/> |4  <br/> |
|下边缘到形状的旋转中心点  <br/> |5  <br/> |
|边界框的中心到 PinX  <br/> |6  <br/> |
|边界框的中心到 PinY  <br/> |7  <br/> |
   

