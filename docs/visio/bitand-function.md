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
description: 返回其中每个位设置为 1 binarynumber1 和 binarynumber2 中相应的位为 1 时才是 16 位二进制数。 否则，将位设置为 0。
ms.openlocfilehash: 0b501bb383596e3f2f39ea14f2cb9eb4bf40b25b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779742"
---
# <a name="bitand-function"></a>BITAND 函数

返回其中每个位设置为 1 binarynumber1 和 binarynumber2 中相应的位为 1 时才是 16 位二进制数。 否则，将位设置为 0。 
  
## <a name="syntax"></a>语法

BITAND (* * *binarynumber1* * *，* * *binarynumber2* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _二进制 number1_ <br/> |必需  <br/> |**Numeric** <br/> |第一个 16 位二进制数。  <br/> |
| _二进制数字 2_ <br/> |必需  <br/> |**Numeric** <br/> |第二个 16 位二进制数。  <br/> |
   
## <a name="remarks"></a>注解

可使用此函数测试和更改那些存储为位掩码（例如形状的文本格式）的形状的属性。
  
## <a name="example"></a>示例

BITAND(12,6)
  
返回 4。12 = 0...01100。6 = 0...00110。因此，BITAND(12,6) = 0...00100。
  

