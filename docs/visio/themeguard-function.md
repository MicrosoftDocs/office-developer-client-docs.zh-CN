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
# <a name="themeguard-function"></a><span data-ttu-id="9b466-103">THEMEGUARD 函数</span><span class="sxs-lookup"><span data-stu-id="9b466-103">THEMEGUARD Function</span></span>

<span data-ttu-id="9b466-104">保护形状的格式单元格，以确保它们使用当前主题的适当方面。</span><span class="sxs-lookup"><span data-stu-id="9b466-104">Guards the formatting cells of a shape to ensure that they use appropriate aspects of the current theme.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="9b466-105">语法</span><span class="sxs-lookup"><span data-stu-id="9b466-105">Syntax</span></span>

<span data-ttu-id="9b466-106">THEMEGUARD () </span><span class="sxs-lookup"><span data-stu-id="9b466-106">THEMEGUARD()</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9b466-107">备注</span><span class="sxs-lookup"><span data-stu-id="9b466-107">Remarks</span></span>

<span data-ttu-id="9b466-108">将 THEMEGUARD 函数应用于单元格并不能保证可以与应用 GUARD 函数相同的方式来保护手动格式。</span><span class="sxs-lookup"><span data-stu-id="9b466-108">Applying the THEMEGUARD function to a cell does not guard against manual formatting in the same way that applying the GUARD function does.</span></span> <span data-ttu-id="9b466-109">如果在用户界面中或通过自动化以编程方式将格式应用于形状，则 THEMEGUARD 公式将被覆盖，除非您在公式中包括 SETATREFEXPR 函数来存储手动格式值。</span><span class="sxs-lookup"><span data-stu-id="9b466-109">If you apply formatting to the shape in the user interface or programmatically, by means of Automation, the THEMEGUARD formula is overridden, unless you include the SETATREFEXPR function in the formula to store the manual formatting value.</span></span> 
  
## <a name="example"></a><span data-ttu-id="9b466-110">示例</span><span class="sxs-lookup"><span data-stu-id="9b466-110">Example</span></span>

```vb
Shape.FillForegnd = THEMEGUARD(THEME("AccentColor2")
```

<span data-ttu-id="9b466-111">指定形状采用当前主题的强调文字颜色 2，而不是采用主要的主题填充颜色。</span><span class="sxs-lookup"><span data-stu-id="9b466-111">Specifies that the shape take the Accent 2 color from the current theme, rather than the main theme fill color.</span></span>
  

