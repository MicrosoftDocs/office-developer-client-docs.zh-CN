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
description: 以字符串形式返回背景页名称。
ms.openlocfilehash: 3b628315052117fe853c8f9c0fc36572de25d871
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410313"
---
# <a name="bkgpagename-function"></a>BKGPAGENAME 函数

以字符串形式返回背景页名称。
  
## <a name="syntax"></a>语法

BKGPAGENAME (** *langID_opt* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _langID_opt_ <br/> |可选  <br/> |**Numeric** <br/> |用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>备注

如果使用函数的页面没有背景页，则返回字符串" \< 无 \> 背景"。 
  
如果传递了非法的语言代码，则将使用本地语言。 
  

