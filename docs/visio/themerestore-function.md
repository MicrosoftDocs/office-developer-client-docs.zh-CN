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
# <a name="themerestore-function"></a><span data-ttu-id="7c7f9-103">THEMERESTORE 函数</span><span class="sxs-lookup"><span data-stu-id="7c7f9-103">THEMERESTORE Function</span></span>

<span data-ttu-id="7c7f9-104">存储形状的局部格式值，以便可以还原局部格式设置如果用户随后删除的主题应用主题时。</span><span class="sxs-lookup"><span data-stu-id="7c7f9-104">Stores the local formatting value of a shape when you apply a theme so that you can restore the local formatting if the user subsequently removes the theme.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7c7f9-105">语法</span><span class="sxs-lookup"><span data-stu-id="7c7f9-105">Syntax</span></span>

<span data-ttu-id="7c7f9-106">THEMERESTORE()</span><span class="sxs-lookup"><span data-stu-id="7c7f9-106">THEMERESTORE()</span></span>
  
## <a name="example"></a><span data-ttu-id="7c7f9-107">示例</span><span class="sxs-lookup"><span data-stu-id="7c7f9-107">Example</span></span>

```vb
Shape.FillForegnd = THEME("FillColor") + THEMERESTORE(RGB(255,102,0)
```

<span data-ttu-id="7c7f9-108">在删除当前主题后，恢复之前应用于形状的局部填充颜色格式。</span><span class="sxs-lookup"><span data-stu-id="7c7f9-108">Restores local fill color formatting previously applied to a shape when the current theme is removed.</span></span>
  

