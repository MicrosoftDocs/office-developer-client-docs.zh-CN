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
description: 返回一个字符串转换为小写形式。
ms.openlocfilehash: da626ee0bb0474fceafcf93ed5c835aacd0034fe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780677"
---
# <a name="lower-function"></a>LOWER 函数

返回一个字符串转换为小写形式。
  
## <a name="syntax"></a>语法

低 (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**因情况而异** <br/> | 字符串、单元格引用或表达式；结果转换为字符串，然后再转换为小写形式。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

大小写转换取决于当前的用户设置，并且特定于区域设置。 
  
## <a name="example"></a>示例

LOWER("mIxEd CAse") 
  
返回“mixed case”。 
  

