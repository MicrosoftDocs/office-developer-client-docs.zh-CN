---
title: BITNOT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251399
localization_priority: Normal
ms.assetid: 7b6486bb-3618-3747-4b00-93bd55767c1c
description: 返回其中每个位设置为 1 中的二进制数相应的位为 0 时才是 16 位二进制数。 否则，将位设置为 0。
ms.openlocfilehash: 0806e7c52cab659a09d27a60efb9c09aa436fb92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779717"
---
# <a name="bitnot-function"></a>BITNOT 函数

返回其中每个位设置为 1 中的二进制数相应的位为 0 时才是 16 位二进制数。 否则，将位设置为 0。
  
## <a name="syntax"></a>语法

BITNOT (* **二进制数** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _二进制数_ <br/> |必需  <br/> |**Numeric** <br/> |一个 16 位二进制数。  <br/> |
   
### <a name="return-value"></a>返回值

16 位二进制数
  
## <a name="example"></a>示例

BITNOT(6)
  
返回 65529。6 = 0...00110。因此，BITNOT(6) = 1...11001。
  

