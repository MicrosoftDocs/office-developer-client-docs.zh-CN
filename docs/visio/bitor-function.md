---
title: BITOR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251400
localization_priority: Normal
ms.assetid: 1d0954c5-b2cb-6c5d-62b3-a68011cf0c85
description: 返回其中每个位设置为 1 如果二进制 number1 或二进制数字 2 中相应的位为 1 16 位二进制数。 仅当二进制 number1 和二进制数字 2 中的相应的位是 0 位设置为 0。
ms.openlocfilehash: db9808f16b32776149abbddf882310c02268cec3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779734"
---
# <a name="bitor-function"></a>BITOR 函数

返回其中每个位设置为 1 如果*二进制 number1*或*二进制数字 2*中相应的位为 1 16 位二进制数。 仅当相应的位*二进制 number1*和*二进制数字 2*中的 0 位设置为 0。 
  
## <a name="syntax"></a>语法

BITOR (* **二进制数字 1* * *，* **二进制数字 2* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _二进制 number1_ <br/> |必需  <br/> |**Numeric** <br/> |第一个 16 位二进制数。  <br/> |
| _二进制数字 2_ <br/> |必需  <br/> |**Numeric** <br/> |第二个 16 位二进制数。  <br/> |
   
### <a name="return-value"></a>返回值

16 位二进制数
  
## <a name="example"></a>示例

BITOR(12,6)
  
返回 14。12 = 0...01100。6 = 0...00110。因此，BITOR(12,6) = 0...01110。
  

