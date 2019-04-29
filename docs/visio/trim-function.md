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
ms.openlocfilehash: b947c9500012d0ceefe3e8044be387f7b810dda9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435717"
---
# <a name="trim-function"></a>TRIM 函数

删除文本中的所有空格，单词之间的单个空格除外。 
  
## <a name="syntax"></a>语法

TRIM (* * *text* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**String** <br/> |要从中删除空格的文本。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>说明

可以对从另一个应用程序接收的、可能包含不规则空格的文本使用 TRIM 函数。
  
## <a name="example"></a>示例

TRIM ("January 1, 2003 ") 
  
返回“January 1, 2003”。 
  

