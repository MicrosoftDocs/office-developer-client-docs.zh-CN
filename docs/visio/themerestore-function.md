---
title: THEMERESTORE 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ca7e6621-f39b-64dd-3594-41d74da21a94
description: 在应用主题时存储形状的局部格式值, 以便在用户随后删除主题时可以还原本地格式设置。
ms.openlocfilehash: 628e246f91172f136dd1a70807fca2abc1ff5bdd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404286"
---
# <a name="themerestore-function"></a>THEMERESTORE 函数

在应用主题时存储形状的局部格式值, 以便在用户随后删除主题时可以还原本地格式设置。
  
## <a name="syntax"></a>语法

THEMERESTORE ()
  
## <a name="example"></a>示例

```vb
Shape.FillForegnd = THEME("FillColor") + THEMERESTORE(RGB(255,102,0)
```

在删除当前主题后，恢复之前应用于形状的局部填充颜色格式。
  

