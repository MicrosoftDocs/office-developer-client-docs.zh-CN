---
title: BITXOR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251401
localization_priority: Normal
ms.assetid: 672eacaf-a374-c7e2-b39b-8d42d2371aee
description: 返回其中每个位设置为 1 如果二进制 number1 和二进制数字 2 但不是能同时中相应的位为 1 16 位二进制数。 否则，将位设置为 0。
ms.openlocfilehash: a0e03258bcfe694dc3bec5469095eff90fb94f1a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779753"
---
# <a name="bitxor-function"></a>BITXOR 函数

返回其中每个位设置为 1 如果二进制 number1 和二进制数字 2 但不是能同时中相应的位为 1 16 位二进制数。 否则，将位设置为 0。
  
## <a name="syntax"></a>语法

BITXOR (* **二进制数字 1* * *，* **二进制数字 2* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _二进制 number1_ <br/> |必需  <br/> |**Numeric** <br/> |第一个 16 位二进制数。  <br/> |
| _二进制数字 2_ <br/> |必需  <br/> |**Numeric** <br/> |第二个 16 位二进制数。  <br/> |
   
### <a name="return-value"></a>返回值

16 位二进制数
  
## <a name="example"></a>示例

BITXOR(12,6)
  
返回 10。12 = 0...01100。6 = 0...00110。因此，BITXOR(12,6) = 0...01010。
  

