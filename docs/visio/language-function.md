---
title: LANGUAGE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e372c670-e9a0-4352-b70a-3a054b036124
description: 允许在不同语言表示形式之间进行比较操作。 它最适用于将 Internet 工程任务组的语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。
ms.openlocfilehash: 9c2dc96cefe7a1cfcd06947dcc54453dcef276fc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327816"
---
# <a name="language-function"></a>LANGUAGE 函数

允许在不同语言表示形式之间进行比较操作。 它最适用于将 Internet 工程任务组的语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **语言**( _lcid_or_bcp47_)
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _lcid_or_bcp47_ <br/> |必需  <br/> |**String** <br/> |语言的 LCID 或 BCP 47 值。  <br/> |
   
## <a name="return-value"></a>返回值

整数
  
## <a name="example"></a>示例

 `LANGUAGE("en-us")`
  
返回值为 "1033"。
  
 `LANGUAGE("es-es")`
  
返回值为 "3082"。
  

