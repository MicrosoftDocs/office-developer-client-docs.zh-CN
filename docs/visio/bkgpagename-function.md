---
title: BKGPAGENAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253219
localization_priority: Normal
ms.assetid: f6e410ef-54d5-9c08-926b-97a2a9786622
description: 作为字符串返回背景页名称。
ms.openlocfilehash: 290fa62242298b3c513bf2870df37204fab31bf3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779774"
---
# <a name="bkgpagename-function"></a>BKGPAGENAME 函数

作为字符串返回背景页名称。
  
## <a name="syntax"></a>语法

BKGPAGENAME (* * *langID_opt* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _langID_opt_ <br/> |可选  <br/> |**Numeric** <br/> |用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>说明

如果使用该函数页上不具有背景页，该字符串"\<没有背景\>"返回。 
  
如果传递了非法的语言代码，则将使用本地语言。 
  

