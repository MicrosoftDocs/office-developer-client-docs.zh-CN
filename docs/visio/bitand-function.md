---
title: BITAND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251398
localization_priority: Normal
ms.assetid: c437de23-d2e0-469d-62e6-8eb8b8cfea5c
description: 返回一个16位二进制数, 只有在 binarynumber1 和 binarynumber2 中的相应位为1时, 才将每位的二进制数设置为1。 否则, 将位设置为0。
ms.openlocfilehash: 495ad645a422c0333d02a22c3c600dd1e0d567bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32284467"
---
# <a name="bitand-function"></a>BITAND 函数

返回一个16位二进制数, 只有在 binarynumber1 和 binarynumber2 中的相应位为1时, 才将每位的二进制数设置为1。 否则, 将位设置为0。 
  
## <a name="syntax"></a>语法

BITAND (* * *binarynumber1* * *, * * *binarynumber2* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _二进制数字1_ <br/> |必需  <br/> |**Numeric** <br/> |第一个 16 位二进制数。  <br/> |
| _二进制数字2_ <br/> |必需  <br/> |**Numeric** <br/> |第二个 16 位二进制数。  <br/> |
   
## <a name="remarks"></a>注解

可使用此函数测试和更改那些存储为位掩码（例如形状的文本格式）的形状的属性。
  
## <a name="example"></a>示例

BITAND (12, 6)
  
返回 4。12 = 0...01100。6 = 0...00110。因此，BITAND(12,6) = 0...00100。
  

