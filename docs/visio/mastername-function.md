---
title: MASTERNAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251581
localization_priority: Normal
ms.assetid: 519d79d4-9178-2231-c26d-aa7f31a43412
description: 以字符串形式返回工作表的主控名称，如果工作表没有主控板，则返回字符串"no master"。
ms.openlocfilehash: 7732cf9e8b23e2fd0fc2e3f2cc8d9ef4f39fd67f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414751"
---
# <a name="mastername-function"></a>MASTERNAME 函数

以字符串形式返回工作表的主控名称，如果工作表没有主控板，则返回字符串"no \< \> master"。
  
## <a name="syntax"></a>语法

MASTERNAME ([ ** *langID_opt* ** ])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _langID_opt_ <br/> |可选  <br/> |**Number** <br/> |用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>备注

如果传递了非法的语言代码，则将使用本地语言。 
  

