---
title: UPPER 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251509
localization_priority: Normal
ms.assetid: ef94ee0f-dbb8-a2e1-1805-8a6609830d2a
description: 返回一个转换为大写的字符串。
ms.openlocfilehash: b88958526bfb5e08839077217759f7ffb50151b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415143"
---
# <a name="upper-function"></a>UPPER 函数

返回一个转换为大写的字符串。
  
## <a name="syntax"></a>语法

UPPER (** *expression* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**变化** <br/> | 可以是字符串、单元格引用或表达式；结果转换为字符串，然后再转换为大写形式。  <br/> |
   
## <a name="remarks"></a>备注

大小写转换取决于当前的用户设置，并且特定于区域设置。 
  
## <a name="example"></a>示例

UPPER("mIxEd CAse") 
  
返回“MIXED CASE”。 
  

