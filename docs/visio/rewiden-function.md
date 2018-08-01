---
title: REWIDEN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033808
localization_priority: Normal
ms.assetid: c20842cd-86b1-83fa-49ba-118936013b6f
description: 将转换公式生成 16 位字符代码的扩大的单字节还是多字节字符集代码，为 16 位 Unicode 字符代码，使用指定的字符集的字符串。
ms.openlocfilehash: 66dc3e801585077a9521cd93f8ae78c47f8a746b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781108"
---
# <a name="rewiden-function"></a>REWIDEN 函数

将转换公式生成 16 位字符代码的扩大的单字节还是多字节字符集代码，为 16 位 Unicode 字符代码，使用指定的字符集的字符串。 
  
## <a name="syntax"></a>语法

REWIDEN (* * *srcCharSet* * *，* * *dstCharSet* * *，* **文本** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _srcCharSet_ <br/> |必需  <br/> |**字符串** <br/> |源文档中的字符集。  <br/> |
| _dstCharSet_ <br/> |必需  <br/> |**字符串** <br/> | 目标文档中的字符集。  <br/> |
| _text_ <br/> |必需  <br/> |**字符串** <br/> |要转换的文本。  <br/> |
   
## <a name="remarks"></a>注解

REWIDEN 函数用于从 Visio 2002 文档到 Visio 2003 文档的自动转换。不建议将该函数用于其他方面。
  

