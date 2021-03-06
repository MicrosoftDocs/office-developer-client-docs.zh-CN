---
title: LANGUAGE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e372c670-e9a0-4352-b70a-3a054b036124
description: 允许在不同语言表示形式之间执行比较操作。 它最适合用于将 Internet 工程任务组语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。
ms.openlocfilehash: 9c2dc96cefe7a1cfcd06947dcc54453dcef276fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424748"
---
# <a name="language-function"></a>LANGUAGE 函数

允许在不同语言表示形式之间执行比较操作。 它最适合用于将 Internet 工程任务组语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **语言**_( lcid_or_bcp47)_
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _lcid_or_bcp47_ <br/> |必需  <br/> |**String** <br/> |语言的 LCID 或 BCP 47 值。  <br/> |
   
## <a name="return-value"></a>返回值

整数
  
## <a name="example"></a>示例

 `LANGUAGE("en-us")`
  
返回值"1033"。
  
 `LANGUAGE("es-es")`
  
返回值"3082"。
  

