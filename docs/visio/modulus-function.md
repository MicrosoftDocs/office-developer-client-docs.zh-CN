---
title: MODULUS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251465
localization_priority: Normal
ms.assetid: cb6326a5-1bf8-b6a3-5c0d-d38c071353a5
description: 返回的结果时数除以除数的余数 （模）。
ms.openlocfilehash: 4e2ef7acf9dc04e788cb2b8a0ff737f12a79c61a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780776"
---
# <a name="modulus-function"></a>MODULUS 函数

返回的结果时数除以除数的余数 （模）。
  
## <a name="syntax"></a>语法

模数 (* **数量** *，* **除数** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**编号** <br/> |被除数。  <br/> |
| _除数_ <br/> |必需  <br/> |**编号** <br/> |除数。  <br/> |
   
### <a name="return-value"></a>返回值

Number
  
## <a name="remarks"></a>注解

结果与除数具有相同的符号。如果除数为 0，则将返回 #DIV/0! 错误。 
  
在绝大多数情况下应使用 MODULUS 函数，而不使用 MOD 函数。 
  
## <a name="example-1"></a>示例 1

MODULUS(5, 1.4)
  
返回 0.8。
  
## <a name="example-2"></a>示例 2

MODULUS(5, -1.4)
  
返回 -0.6。
  
## <a name="example-3"></a>示例 3

MODULUS(-5, 1.4)
  
返回 0.6。
  
## <a name="example-4"></a>示例 4

MODULUS(-5, -1.4)
  
返回 -0.8。
  

