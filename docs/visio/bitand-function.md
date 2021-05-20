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
description: 返回一个 16 位二进制数，只有当 binarynumber1 和 binarynumber2 中的对应位都为 1 时，每个位才被设置为 1。 否则，将位设置为 0。
ms.openlocfilehash: a3c76a9122d0f02d5ab61460cf3457bb15da4d7b
ms.sourcegitcommit: 939bd9686ba41a8f94b82e004ed84b9054d9c7cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48293490"
---
# <a name="bitand-function"></a>BITAND 函数

返回一个 16 位二进制数，只有当 binarynumber1 和 binarynumber2 中的对应位都为 1 时，每个位才被设置为 1。 否则，将位设置为 0。 
  
## <a name="syntax"></a>语法

BITAND (***binarynumber1***、 ***binarynumber2*** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _binary number1_ <br/> |必需  <br/> |**Numeric** <br/> |第一个 16 位二进制数。  <br/> |
| _binary number2_ <br/> |必需  <br/> |**Numeric** <br/> |第二个 16 位二进制数。  <br/> |
   
## <a name="remarks"></a>备注

可使用此函数测试和更改那些存储为位掩码（例如形状的文本格式）的形状的属性。
  
## <a name="example"></a>示例

BITAND (12，6) 
  
返回 4。12 = 0...01100。6 = 0...00110。因此，BITAND(12,6) = 0...00100。
  

