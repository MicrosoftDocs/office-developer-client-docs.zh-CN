---
title: TRIM 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027318
localization_priority: Normal
ms.assetid: 6f2d84fd-27eb-4c2f-a2e1-43d20e0c78be
description: 删除文本中的所有空格，单词之间的单个空格除外。
ms.openlocfilehash: b396572041e880451ceb1ec6f0508528c0807bfc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781565"
---
# <a name="trim-function"></a>TRIM 函数

删除文本中的所有空格，单词之间的单个空格除外。 
  
## <a name="syntax"></a>语法

修整 (* **文本** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**字符串** <br/> |要从中删除空格的文本。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

可以对从另一个应用程序接收的、可能包含不规则空格的文本使用 TRIM 函数。
  
## <a name="example"></a>示例

TRIM ("January 1, 2003 ") 
  
返回“January 1, 2003”。 
  

