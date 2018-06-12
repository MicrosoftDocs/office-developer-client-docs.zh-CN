---
title: THEMEGUARD 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a556eadc-9ee6-7a29-ca05-6250b612790c
description: 保护以确保它们使用当前主题的相应方面的形状的格式的单元格。
ms.openlocfilehash: 10a7772995b9cc22e53ff577b2f663d7c97d0816
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781511"
---
# <a name="themeguard-function"></a>THEMEGUARD 函数

保护以确保它们使用当前主题的相应方面的形状的格式的单元格。
  
## <a name="syntax"></a>语法

THEMEGUARD()
  
## <a name="remarks"></a>注解

对单元格应用 THEMEGUARD 函数不能防范相同的方式，应用 GUARD 函数执行手动设定的格式。 如果您将格式应用于该形状在用户界面中或以编程方式，通过自动化，则将被覆盖 THEMEGUARD 公式，除非您在公式中存储的手动格式值包含 SETATREFEXPR 函数。 
  
## <a name="example"></a>示例

```vb
Shape.FillForegnd = THEMEGUARD(THEME("AccentColor2")
```

指定形状采用当前主题的强调文字颜色 2，而不是采用主要的主题填充颜色。
  

