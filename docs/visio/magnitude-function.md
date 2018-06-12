---
title: MAGNITUDE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251461
localization_priority: Normal
ms.assetid: 9f443687-9861-5f51-94c4-f056805f736b
description: 将返回向量程度其矢高是 A 和 B，乘以各自其运行常量 constantA 和 constantB。
ms.openlocfilehash: f4c428b8b381af58958dab66a71ddd0bcaf715c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780681"
---
# <a name="magnitude-function"></a>MAGNITUDE 函数

将返回向量程度其矢高是_A_和_B_，乘以各自常量其运行_constantA_和_constantB_。 
  
## <a name="syntax"></a>语法

MAGNITUDE (* * *constantA* * *，* * *A* * *，* * *constantB* * *，* * *B* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _constantA_ <br/> |必需  <br/> |**编号** <br/> |矢高要乘以的常量。  <br/> |
| _A_ <br/> |必需  <br/> |**编号** <br/> |矢高。  <br/> |
| _constantB_ <br/> |必需  <br/> |**编号** <br/> |游程要乘以的常量。  <br/> |
| _B_ <br/> |必需  <br/> |**编号** <br/> |游程。  <br/> |
   
## <a name="remarks"></a>注解

MAGNITUDE 按照以下公式计算：
  
SQRT ((constantA \* A) ^2 + (constantB \* B) ^2)
  
## <a name="example"></a>示例

MAGNITUDE(1, 3, 1, 4) 
  
返回 5。 
  

