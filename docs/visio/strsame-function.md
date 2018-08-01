---
title: STRSAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251786
localization_priority: Normal
ms.assetid: d9fc2007-cc21-b20c-adee-be87cc356753
description: 确定字符串是否相同。 如果它们是相同的则返回 TRUE 和 FALSE 如果它们不是。
ms.openlocfilehash: 5365ce6e679f708a47f4bcbdebbc4cabb13a2aee
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781436"
---
# <a name="strsame-function"></a>STRSAME 函数

确定字符串是否相同。 如果它们是相同的则返回 TRUE 和 FALSE 如果它们不是。 
  
## <a name="syntax"></a>语法

STRSAME ("* * *string1* * *"，"* * *string2* * *"，* * *ignoreCase* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _string1_ <br/> |必需  <br/> |**字符串** <br/> |要比较的第一个字符串。  <br/> |
| _string2_ <br/> |必需  <br/> |**字符串** <br/> |要比较的第二个字符串。  <br/> |
| _ignoreCase_ <br/> |可选  <br/> |**Boolean** <br/> |TRUE 为忽略大小写，FALSE 为比较大小写。默认值为 FALSE。  <br/> |
   
### <a name="return-value"></a>返回值

Boolean
  
## <a name="remarks"></a>注解

若要比较多字节字符串或使用特定区域设置的大小写规则进行比较，请使用 STRSAMEEX 函数。
  
## <a name="example-1"></a>示例 1

STRSAME("cat","dog")
  
返回 FALSE。
  
## <a name="example-2"></a>示例 2

STRSAME("cat","cat")
  
返回 TRUE。
  
## <a name="example-3"></a>示例 3

STRSAME("cat","cat", TRUE)
  
返回 TRUE。
  
## <a name="example-4"></a>示例 4

STRSAME("cat","CAT")
  
返回 FALSE。
  
## <a name="example-5"></a>示例 5

STRSAME("cat","CAT", TRUE)
  
返回 TRUE。
  
## <a name="example-6"></a>示例 6

STRSAME("cät,"CAT", TRUE)
  
返回 FALSE。
  
## <a name="example-7"></a>示例 7

STRSAME("cät,"CÄT", TRUE)
  
返回 TRUE。
  

