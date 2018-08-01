---
title: INDEX 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251443
localization_priority: Normal
ms.assetid: cc46f91e-733f-e25a-17d2-19df8c8febd2
description: 在用 delimiter 分隔的 list 中返回位于从零开始的位置 index 的子字符串。如果索引超出范围，则返回一个空字符串或返回作为 errorvalue 参数提供的可选令牌。
ms.openlocfilehash: b801f3b2a762f7767f32953806178be3eb264398
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780444"
---
# <a name="index-function"></a>INDEX 函数

返回在由_分隔符_分隔的_列表_的从零开始的位置的_索引_处的子字符串。 或者，如果索引超出范围，返回作为*errorvalue*参数提供为空字符串或的可选标记。 
  
## <a name="syntax"></a>语法

索引 (* **索引** *，"* **列表** *"[，[* **分隔符** *] [，[* * *errorvalue* * *]]]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _index_ <br/> |必需  <br/> |**编号** <br/> |要查找的位置。  <br/> |
| _列表_ <br/> |必需  <br/> |**字符串** <br/> |要在其中进行搜索的列表。  <br/> |
| _分隔符_ <br/> |可选  <br/> |**字符串** <br/> | 要使用作为分隔符_列表_中的字符串。 _分隔符_字符串可以为多个字符的长度，并且包含多字节字符。 默认值为分号。  <br/> |
| _errorvalue_ <br/> |可选  <br/> |**编号** <br/> | 用户指定的在索引超出范围时返回的值。默认值是一个空字符串。  <br/> |
   
## <a name="remarks"></a>注解

如果列表以一个分隔符开始或结束，则认为在列表前或列表后存在一个空字符串。连续的分隔符表示其间为空字符串。 
  
如果索引超出范围，Visio 将返回空字符串或作为*errorvalue*参数提供的可选标记。 
  
## <a name="example-1"></a>示例 1

INDEX(3,"cat;rat;;goat")
  
返回“goat”。
  
## <a name="example-2"></a>示例 2

INDEX(54,";1;2;3;",,"ERROR")
  
返回“ERROR”。
  

