---
title: THEMEGUARD 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a556eadc-9ee6-7a29-ca05-6250b612790c
description: 保护形状的格式单元格，以确保它们使用当前主题的适当方面。
ms.openlocfilehash: c20d43f9d03296a3c529a6c8f59cf27489dcdc51
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404944"
---
# <a name="themeguard-function"></a>THEMEGUARD 函数

保护形状的格式单元格，以确保它们使用当前主题的适当方面。
  
## <a name="syntax"></a>语法

THEMEGUARD () 
  
## <a name="remarks"></a>备注

将 THEMEGUARD 函数应用于单元格并不能保证可以与应用 GUARD 函数相同的方式来保护手动格式。 如果在用户界面中或通过自动化以编程方式将格式应用于形状，则 THEMEGUARD 公式将被覆盖，除非您在公式中包括 SETATREFEXPR 函数来存储手动格式值。 
  
## <a name="example"></a>示例

```vb
Shape.FillForegnd = THEMEGUARD(THEME("AccentColor2")
```

指定形状采用当前主题的强调文字颜色 2，而不是采用主要的主题填充颜色。
  

