---
title: LOCTOLOC 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251586
localization_priority: Normal
ms.assetid: 1f09482a-0b1b-1bef-bc23-7f7793c4c65f
description: 返回目标坐标系中用本地坐标表示的转换点。
ms.openlocfilehash: f08feb6137c3022027d19b45f06285fb8b6441a7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427484"
---
# <a name="loctoloc-function"></a>LOCTOLOC 函数

返回目标坐标系中用本地坐标表示的转换点。
  
## <a name="syntax"></a>语法

LOCTOLOC (** *srcPoint* **， ** *srcRef* **， ** *dstRef* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _srcPoint_ <br/> |必需  <br/> |**String** <br/> | 用源坐标系中的本地坐标表示的点。  <br/> |
| _srcRef_ <br/> |必需  <br/> |**String** <br/> | 对源对象中的单元格的引用。  <br/> |
| _dstRef_ <br/> |必需  <br/> |**String** <br/> | 对目标对象中的单元格的引用。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>备注

LOCTOLOC 函数将用源形状中的本地坐标表示的点转换用目标形状中的本地坐标表示的点。您可以使用此函数构造一个形状，例如，依据距离另一个坐标空间的点。您还可以使用此函数将本地点转换为页坐标，反之亦然。
  
即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。
  
源坐标和目标坐标必须位于同一页上。
  
## <a name="example"></a>示例

下面的公式将与公式相关联的形状的本地旋转中心点转换为页上的点。
  
```vb
LOCTOLOC(PNT(LocPinX, LocPinY), Width, ThePage!PageWidth)
```


