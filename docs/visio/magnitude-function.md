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
description: 返回一个向量的大小, 该向量的升为, 其运行为 B, 乘以各自的常量 constantA 和 constantB。
ms.openlocfilehash: 6393c7827e2553ca4948c8b9c51075ca8e4783bd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420456"
---
# <a name="magnitude-function"></a>MAGNITUDE 函数

返回_一个_向量的大小, 该向量的升为, 其运行为_B_, 乘以各自的常量_constantA_和_constantB_。 
  
## <a name="syntax"></a>语法

数量级 (* * *constantA* * *, * * *A* * *, * * *constantB* * *, * * *B* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _constantA_ <br/> |必需  <br/> |**Number** <br/> |矢高要乘以的常量。  <br/> |
| _A_ <br/> |必需  <br/> |**Number** <br/> |矢高。  <br/> |
| _constantB_ <br/> |必需  <br/> |**Number** <br/> |游程要乘以的常量。  <br/> |
| _黑白_ <br/> |必需  <br/> |**Number** <br/> |游程。  <br/> |
   
## <a name="remarks"></a>说明

MAGNITUDE 按照以下公式计算：
  
SQRT ((constantA \* A) ^ 2 + (constantB \* B) ^ 2)
  
## <a name="example"></a>示例

MAGNITUDE(1, 3, 1, 4) 
  
返回 5。 
  

