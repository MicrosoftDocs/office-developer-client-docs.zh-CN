---
title: LOWER 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251459
localization_priority: Normal
ms.assetid: 1d198ea6-49e0-e462-b2cf-b65fbb920b55
description: 返回一个转换为小写形式的字符串。
ms.openlocfilehash: 275e5cc40bed5c3ca7d6f40b0882f523334611c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421240"
---
# <a name="lower-function"></a>LOWER 函数

返回一个转换为小写形式的字符串。
  
## <a name="syntax"></a>语法

下限 (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**相同** <br/> | 字符串、单元格引用或表达式；结果转换为字符串，然后再转换为小写形式。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>说明

大小写转换取决于当前的用户设置，并且特定于区域设置。 
  
## <a name="example"></a>示例

LOWER("mIxEd CAse") 
  
返回“mixed case”。 
  

