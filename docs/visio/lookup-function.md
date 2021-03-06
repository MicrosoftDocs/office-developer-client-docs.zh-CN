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
ms.openlocfilehash: 10fc32e6e979ab819246161dedfb1183c2683a99
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410327"
---
# <a name="lookup-function"></a>LOOKUP 函数

返回一个从零开始索引，该索引指示子字符串键在列表中的位置，如果目标字符串包含分隔 _符_，则返回 -1。
  
## <a name="syntax"></a>语法

LOOKUP (" ** *key* ** "，" ** *list* ** "[，" ** *delimiter* ** "])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _key_ <br/> |必需  <br/> |**String** <br/> |要查找的字符串。  <br/> |
| _列表_ <br/> |必需  <br/> |**String** <br/> | 要在其中进行搜索的列表。  <br/> |
| _delimiter_ <br/> |可选  <br/> |**字符串** <br/> | 要用作列表 内分隔符的  _字符串_。 _分隔符字符串_ 的长度可以超过一个字符，并且可以包含多字节字符。 默认值是一个分号。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric
  
## <a name="remarks"></a>备注

LOOKUP 函数使用不区分大小写的搜索。如果列表以一个分隔符开始或结束，则认为在列表前或列表后存在一个空字符串。连续的分隔符表示其间为空字符串。 
  
所有参数都必须是字符串，或能够转换为字符串的表达式。否则，空字符串将替代有问题的参数。 
  
## <a name="example-1"></a>示例 1

LOOKUP ("，cat;rat;;") 
  
返回 1。
  
## <a name="example-2"></a>示例 2

LOOKUP ("，";cat;rat;;") 
  
返回 0。
  
## <a name="example-3"></a>示例 3

LOOKUP ("t"，"cat;rat;;"，"a") 
  
返回 3。
  

