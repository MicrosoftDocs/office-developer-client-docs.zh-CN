---
title: 语言函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e372c670-e9a0-4352-b70a-3a054b036124
description: 允许不同的语言表示之间的比较操作。 它最适用于将 Internet 工程任务组语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。
ms.openlocfilehash: 6a05a850f5908ac5a4f6a4a72b2ce56b4c98f137
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780544"
---
# <a name="language-function"></a>语言函数

允许不同的语言表示之间的比较操作。 它最适用于将 Internet 工程任务组语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013 
  
## <a name="syntax"></a>语法

 **语言**( _lcid_or_bcp47_)
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _lcid_or_bcp47_ <br/> |必需  <br/> |**字符串** <br/> |语言的 LCID 或 BCP 47 值。  <br/> |
   
## <a name="return-value"></a>返回值

Integer
  
## <a name="example"></a>示例

 `LANGUAGE("en-us")`
  
返回的值为"1033"。
  
 `LANGUAGE("es-es")`
  
返回的值为"3082"。
  

