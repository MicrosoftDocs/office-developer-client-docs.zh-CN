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
description: 使用指定的字符集将生成 16 位字符代码的公式转换为 16 位 Unicode 字符代码的字符串，这些代码扩展了单字节或多字节字符集代码。
ms.openlocfilehash: c885487f91e541027b7ba09812e7321a9deb00ac
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405210"
---
# <a name="rewiden-function"></a>REWIDEN 函数

使用指定的字符集将生成 16 位字符代码的公式转换为 16 位 Unicode 字符代码的字符串，这些代码扩展了单字节或多字节字符集代码。 
  
## <a name="syntax"></a>语法

REWIDEN (** *srcCharSet* **， ** *dstCharSet* **， ** *text* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _srcCharSet_ <br/> |必需  <br/> |**String** <br/> |源文档中的字符集。  <br/> |
| _dstCharSet_ <br/> |必需  <br/> |**String** <br/> | 目标文档中的字符集。  <br/> |
| _text_ <br/> |必需  <br/> |**String** <br/> |要转换的文本。  <br/> |
   
## <a name="remarks"></a>备注

REWIDEN 函数用于从 Visio 2002 文档到 Visio 2003 文档的自动转换。不建议将该函数用于其他方面。
  

