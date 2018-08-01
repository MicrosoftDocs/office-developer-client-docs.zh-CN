---
title: ASIN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251395
localization_priority: Normal
ms.assetid: 7d917be4-65b1-002f-48cc-6d81916a1157
description: 返回一个数字，例如，正弦值为 number 的角度的反正弦。
ms.openlocfilehash: e5ed8f9fc8c85ac4816fede03bfe6f6af5cbf5f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779677"
---
# <a name="asin-function"></a>ASIN 函数

返回一个数字，例如，正弦为*数字*的角度的反正弦。 
  
## <a name="syntax"></a>语法

ASIN (* **数量** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Numeric** <br/> |角度的正弦值。  <br/> |
   
## <a name="remarks"></a>注解

输入的值必须位于范围介于-1 < =*号码*< = 1 或 #NUM ！ 将返回错误。 生成的角度位于范围-PI/2 < =*角度*< = PI/2 弧度 (-90 < =*角度*< = 90 度)。 
  
## <a name="example"></a>示例

ASIN(1)
  
返回 90 度
  

