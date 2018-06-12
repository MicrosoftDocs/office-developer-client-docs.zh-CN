---
title: THEMERESTORE 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ca7e6621-f39b-64dd-3594-41d74da21a94
description: 存储形状的局部格式值，以便可以还原局部格式设置如果用户随后删除的主题应用主题时。
ms.openlocfilehash: f22f603cad1d310adc59d19e9b3e3882bd797fce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781524"
---
# <a name="themerestore-function"></a>THEMERESTORE 函数

存储形状的局部格式值，以便可以还原局部格式设置如果用户随后删除的主题应用主题时。
  
## <a name="syntax"></a>语法

THEMERESTORE()
  
## <a name="example"></a>示例

```vb
Shape.FillForegnd = THEME("FillColor") + THEMERESTORE(RGB(255,102,0)
```

在删除当前主题后，恢复之前应用于形状的局部填充颜色格式。
  

