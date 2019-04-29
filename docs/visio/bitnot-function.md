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
description: 返回一个16位二进制数, 只有当二进制数中的对应位为0时, 才将每位的二进制数设置为1。 否则, 将位设置为0。
ms.openlocfilehash: 34ea6fd614feae8e3c8e97e34b7ff6c531f4c123
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438832"
---
# <a name="bitnot-function"></a>BITNOT 函数

返回一个16位二进制数, 只有当二进制数中的对应位为0时, 才将每位的二进制数设置为1。 否则, 将位设置为0。
  
## <a name="syntax"></a>语法

BITNOT (* **二进制数** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _二进制数_ <br/> |必需  <br/> |**数值** <br/> |一个 16 位二进制数。  <br/> |
   
### <a name="return-value"></a>返回值

16 位二进制数
  
## <a name="example"></a>示例

BITNOT (6)
  
返回 65529。6 = 0...00110。因此，BITNOT(6) = 1...11001。
  

