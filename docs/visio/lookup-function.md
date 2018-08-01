---
title: LOOKUP 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251457
localization_priority: Normal
ms.assetid: cb6ec664-6062-75d0-1514-8058b98c2c36
description: 返回基于零的索引，该索引指示子字符串 key 在 list 中的位置，或者如果目标字符串包含 delimiter，则返回 -1。
ms.openlocfilehash: e1fd433282871135d385d1c980c77041cd49cdf4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780669"
---
# <a name="lookup-function"></a>LOOKUP 函数

返回一个从零开始的索引，它指示的位置的子字符串_键_在_列表_中，则返回-1，如果目标字符串包含_分隔符_。
  
## <a name="syntax"></a>语法

查找 ("* **键** *"、"* **列表** *"[，"* **分隔符** *"]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**Description**|
|:-----|:-----|:-----|:-----|
| _key_ <br/> |必需  <br/> |**字符串** <br/> |要查找的字符串。  <br/> |
| _列表_ <br/> |必需  <br/> |**字符串** <br/> | 要在其中进行搜索的列表。  <br/> |
| _分隔符_ <br/> |可选  <br/> |**字符串** <br/> | 要使用作为分隔符_列表_中的字符串。 _分隔符_字符串可以为多个字符的长度，并且可能包含多字节字符。 默认值为分号。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric
  
## <a name="remarks"></a>注解

LOOKUP 函数使用不区分大小写的搜索。如果列表以一个分隔符开始或结束，则认为在列表前或列表后存在一个空字符串。连续的分隔符表示其间为空字符串。 
  
所有参数都必须是字符串，或能够转换为字符串的表达式。否则，空字符串将替代有问题的参数。 
  
## <a name="example-1"></a>示例 1

LOOKUP("rat","cat;rat;;goat")
  
返回 1。
  
## <a name="example-2"></a>示例 2

LOOKUP("",";cat;rat;;goat")
  
返回 0。
  
## <a name="example-3"></a>示例 3

LOOKUP("t","cat;rat;;goat","a")
  
返回 3。
  

