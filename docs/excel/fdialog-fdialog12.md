---
title: fDialog/fDialog12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fDialog
- fDialog12
keywords:
- fdialog 函数 [excel 2007], fDialog12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: a9a47408-07d1-4a00-9596-abc48b12392f
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 58d0df500c38534ec1315d2dab1517c1f5272ad5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304065"
---
# <a name="fdialogfdialog12"></a><span data-ttu-id="2a839-104">fDialog/fDialog12</span><span class="sxs-lookup"><span data-stu-id="2a839-104">fDialog/fDialog12</span></span>

 <span data-ttu-id="2a839-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a839-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2a839-106">演示如何使用 C API 中的对话框功能在 DLL 中创建 Microsoft Excel UDD (用户定义的对话框) 的用户定义命令示例。</span><span class="sxs-lookup"><span data-stu-id="2a839-106">Example user-defined command that demonstrates how to create a Microsoft Excel UDD (user-defined dialog box) within a DLL by using the dialog box capabilities in the C API.</span></span> <span data-ttu-id="2a839-107">当加载了 generic xll 时, 它将创建一个用户定义的菜单 (通用), 通过该菜单可访问此命令。</span><span class="sxs-lookup"><span data-stu-id="2a839-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span>
  
```cs
int WINAPI fDialog(void);
```

## <a name="parameters"></a><span data-ttu-id="2a839-108">参数</span><span class="sxs-lookup"><span data-stu-id="2a839-108">Parameters</span></span>

<span data-ttu-id="2a839-109">函数不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="2a839-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2a839-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="2a839-110">Property value/Return value</span></span>

<span data-ttu-id="2a839-111">函数总是返回1。</span><span class="sxs-lookup"><span data-stu-id="2a839-111">The function always returns 1.</span></span>
  
### <a name="example"></a><span data-ttu-id="2a839-112">示例</span><span class="sxs-lookup"><span data-stu-id="2a839-112">Example</span></span>

<span data-ttu-id="2a839-113">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="2a839-113">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2a839-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a839-114">See also</span></span>



[<span data-ttu-id="2a839-115">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="2a839-115">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

