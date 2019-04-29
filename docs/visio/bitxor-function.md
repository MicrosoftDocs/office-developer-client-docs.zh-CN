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
description: 返回一个16位二进制数, 在该数字中, 如果二进制数字1和二进制数字2中的相应位不同时为 1, 则将每位设置为1。 否则, 将位设置为0。
ms.openlocfilehash: ab8ff46fe98512d963ef4ecd5c37127353827725
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439231"
---
# <a name="bitxor-function"></a>BITXOR 函数

返回一个16位二进制数, 在该数字中, 如果二进制数字1和二进制数字2中的相应位不同时为 1, 则将每位设置为1。 否则, 将位设置为0。
  
## <a name="syntax"></a>语法

BITXOR (* * *binary 1* * *, * **二进制数字 2* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _二进制数字1_ <br/> |必需  <br/> |**数值** <br/> |第一个 16 位二进制数。  <br/> |
| _二进制数字2_ <br/> |必需  <br/> |**数值** <br/> |第二个 16 位二进制数。  <br/> |
   
### <a name="return-value"></a>返回值

16 位二进制数
  
## <a name="example"></a>示例

BITXOR (12, 6)
  
返回 10。12 = 0...01100。6 = 0...00110。因此，BITXOR(12,6) = 0...01010。
  

