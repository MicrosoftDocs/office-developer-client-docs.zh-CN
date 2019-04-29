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
description: 返回一个16位二进制数, 其中如果二进制数字1或二进制数字2中的相应位为 1, 则将每位的二进制数设置为1。 仅当二进制数字1和二进制数字2中对应的位为0时, 位才设置为0。
ms.openlocfilehash: 13bda2c6c65557b1f8372432cf919b2aaf2d75de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408080"
---
# <a name="bitor-function"></a>BITOR 函数

返回一个16位二进制数, 其中如果*二进制*数字1或*二进制数字 2*中的相应位为 1, 则将每位的二进制数设置为1。 仅当*二进制数字 1*和*二进制数字 2*中对应的位为0时, 位才设置为0。 
  
## <a name="syntax"></a>语法

BITOR (* * *binary 1* * *, * **二进制数字 2* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _二进制数字1_ <br/> |必需  <br/> |**数值** <br/> |第一个 16 位二进制数。  <br/> |
| _二进制数字2_ <br/> |必需  <br/> |**数值** <br/> |第二个 16 位二进制数。  <br/> |
   
### <a name="return-value"></a>返回值

16 位二进制数
  
## <a name="example"></a>示例

BITOR (12, 6)
  
返回 14。12 = 0...01100。6 = 0...00110。因此，BITOR(12,6) = 0...01110。
  

