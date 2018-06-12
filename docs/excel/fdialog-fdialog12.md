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
- fdialog 函数 [excel 2007，] fDialog12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: a9a47408-07d1-4a00-9596-abc48b12392f
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 554b76d2d316110286e83158acfff33aa68e19c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773744"
---
# <a name="fdialogfdialog12"></a><span data-ttu-id="6937f-104">fDialog/fDialog12</span><span class="sxs-lookup"><span data-stu-id="6937f-104">fDialog/fDialog12</span></span>

 <span data-ttu-id="6937f-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6937f-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="6937f-106">示例用户定义演示如何使用 C API 中的对话框框功能创建 Microsoft Excel UDD （用户定义的对话框中） DLL 中的命令。</span><span class="sxs-lookup"><span data-stu-id="6937f-106">Example user-defined command that demonstrates how to create a Microsoft Excel UDD (user-defined dialog box) within a DLL by using the dialog box capabilities in the C API.</span></span> <span data-ttu-id="6937f-107">当加载 GENERIC.xll 时，它会创建用户定义的菜单中，一般，通过其访问此命令。</span><span class="sxs-lookup"><span data-stu-id="6937f-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span>
  
```cs
int WINAPI fDialog(void);
```

## <a name="parameters"></a><span data-ttu-id="6937f-108">参数</span><span class="sxs-lookup"><span data-stu-id="6937f-108">Parameters</span></span>

<span data-ttu-id="6937f-109">函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="6937f-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6937f-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="6937f-110">Property value/Return value</span></span>

<span data-ttu-id="6937f-111">此函数始终返回 1。</span><span class="sxs-lookup"><span data-stu-id="6937f-111">The function always returns 1.</span></span>
  
### <a name="example"></a><span data-ttu-id="6937f-112">示例</span><span class="sxs-lookup"><span data-stu-id="6937f-112">Example</span></span>

<span data-ttu-id="6937f-113">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="6937f-113">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6937f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6937f-114">See also</span></span>



[<span data-ttu-id="6937f-115">泛型 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="6937f-115">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

