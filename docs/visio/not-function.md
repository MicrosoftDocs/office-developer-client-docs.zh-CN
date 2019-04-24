---
title: NOT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251469
localization_priority: Normal
ms.assetid: 65873b32-2406-7c33-8e68-802461f467b2
description: 如果 logicalexpression 为 FALSE, 则返回 TRUE (1)。 否则, 它将返回 FALSE (0)。
ms.openlocfilehash: 3359e21654bcc318caf31405093f851eca064119
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341136"
---
# <a name="not-function"></a>NOT 函数

如果_logicalexpression_为 FALSE, 则返回 TRUE (1)。 否则, 它将返回 FALSE (0)。 
  
## <a name="syntax"></a>语法

NOT (* * *logicalexpression* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _logicalexpression_ <br/> |必需  <br/> |**String** <br/> |要计算的逻辑表达式。  <br/> |
   
### <a name="return-value"></a>返回值

布尔值
  
## <a name="example"></a>示例

不是 ( \>高度 0.75 in) 
  
如果高度小于或等于 0.75 英寸，则返回 1。 如果高度大于 0.75 英寸，则返回 0。 
  

