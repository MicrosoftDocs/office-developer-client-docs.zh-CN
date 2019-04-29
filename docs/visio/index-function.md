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
description: 在用 delimiter 分隔的 list 中返回位于从零开始的位置 index 的子字符串。 如果索引超出范围，则返回一个空字符串或返回作为 errorvalue 参数提供的可选令牌。
ms.openlocfilehash: 11362ed984a489682d57f007300e60de548ddf11
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431573"
---
# <a name="index-function"></a>INDEX 函数

返回以_分隔符_分隔的_列表_中从零开始的位置_索引_处的子字符串。 或者, 如果索引超出范围, 则返回一个空字符串或作为*errorvalue*参数提供的可选令牌。 
  
## <a name="syntax"></a>语法

index (* **索引** *, "* * *list* * *" [, [* **分隔符** *] [, [* * *errorvalue* * *]]]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _index_ <br/> |必需  <br/> |**Number** <br/> |要查找的位置。  <br/> |
| _列表_ <br/> |必需  <br/> |**String** <br/> |要在其中进行搜索的列表。  <br/> |
| _分隔符_ <br/> |可选  <br/> |**字符串** <br/> | 要用作_列表_中的分隔符的字符串。 _分隔符_串的长度不能超过一个字符, 并且包含多字节字符。 默认值是一个分号。  <br/> |
| _errorvalue_ <br/> |可选  <br/> |**Number** <br/> | 用户指定的在索引超出范围时返回的值。 默认值是一个空字符串。  <br/> |
   
## <a name="remarks"></a>说明

如果列表以一个分隔符开始或结束，则认为在列表前或列表后存在一个空字符串。连续的分隔符表示其间为空字符串。 
  
如果索引超出范围, Visio 将返回一个空字符串或作为*errorvalue*参数提供的可选令牌。 
  
## <a name="example-1"></a>示例 1

索引 (3, "cat; rat;;goat ")
  
返回“goat”。
  
## <a name="example-2"></a>示例 2

索引 (54, "; 1; 2; 3;",, "错误")
  
返回“ERROR”。
  

