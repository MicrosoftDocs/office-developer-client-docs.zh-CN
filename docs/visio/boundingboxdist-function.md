---
title: BOUNDINGBOXDIST 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8a2490f2-48c4-5df3-a3b3-40e8e0c80479
description: 返回形状边界框的指定部分的度量。
ms.openlocfilehash: a62d5b82c310e7b99e16b70982b75a68172b7fd8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428275"
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
| _Index_ <br/> |必需  <br/> |**Number** <br/> |要测量和返回的形状边界框的一部分。 有关可能值，请参见备注。  <br/> |
   
### <a name="return-value"></a>返回值

 **Number**
  
## <a name="remarks"></a>说明

 *索引*可以是下列值之一。 
  
|**项**|**值**|
|:-----|:-----|
|Width  <br/> |0  <br/> |
|Height  <br/> |1  <br/> |
|左边缘到形状的旋转中心点  <br/> |双面  <br/> |
|形状的旋转中心点到右边缘  <br/> |第三章  <br/> |
|形状的旋转中心点到上边缘  <br/> |4  <br/> |
|下边缘到形状的旋转中心点  <br/> |5  <br/> |
|边界框的中心到 PinX  <br/> |型  <br/> |
|边界框的中心到 PinY  <br/> |步  <br/> |
   

