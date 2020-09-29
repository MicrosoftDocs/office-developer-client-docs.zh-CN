---
title: ASIN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251395
localization_priority: Normal
ms.assetid: 7d917be4-65b1-002f-48cc-6d81916a1157
description: 返回一个数的反正弦值，例如，其正弦为数字的角度。
ms.openlocfilehash: e66ed9ab3d01ac79bceb18f5c793afc928e5e4b4
ms.sourcegitcommit: 939bd9686ba41a8f94b82e004ed84b9054d9c7cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48293504"
---
# <a name="asin-function"></a>ASIN 函数

返回一个数的反正弦值，例如，其正弦为  *数字*  的角度。 
  
## <a name="syntax"></a>语法

ASIN (***号*** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**数值** <br/> |角度的正弦值。  <br/> |
   
## <a name="remarks"></a>说明

输入值必须在范围-1 <=  *number*  <= 1 或 #NUM！ 错误。 生成的角度在范围-PI/2 <=  *角度*  <= PI/2 弧度 (-90 <=  *角*  <= 90 度) 。 
  
## <a name="example"></a>示例

ASIN (1) 
  
返回 90 度
  

