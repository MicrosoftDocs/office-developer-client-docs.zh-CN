---
title: fShowDialog
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fShowDialog
keywords:
- fshowdialog 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 6cc01075-7221-488e-870f-433da62930e6
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 6122e4b99c69cd1bd878c9267ff85f59d0f61998
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433589"
---
# <a name="fshowdialog"></a><span data-ttu-id="0302e-104">fShowDialog</span><span class="sxs-lookup"><span data-stu-id="0302e-104">fShowDialog</span></span>

 <span data-ttu-id="0302e-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0302e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="0302e-106">用户定义的示例命令，用于加载并显示示例本机Windows对话框。</span><span class="sxs-lookup"><span data-stu-id="0302e-106">Example user-defined command that loads and displays an example native Windows dialog box.</span></span> <span data-ttu-id="0302e-107">加载 GENERIC.xll 时，它将创建一个用户定义的菜单 Generic，通过该菜单可以访问此命令。</span><span class="sxs-lookup"><span data-stu-id="0302e-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span>
  
```cs
int WINAPI fShowDialog(void);
```

## <a name="parameters"></a><span data-ttu-id="0302e-108">参数</span><span class="sxs-lookup"><span data-stu-id="0302e-108">Parameters</span></span>

<span data-ttu-id="0302e-109">该函数不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="0302e-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0302e-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="0302e-110">Property value/Return value</span></span>

<span data-ttu-id="0302e-111">函数返回整数 0 以指示成功完成</span><span class="sxs-lookup"><span data-stu-id="0302e-111">The function return integer zero to indicate successful completion</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0302e-112">备注</span><span class="sxs-lookup"><span data-stu-id="0302e-112">Remarks</span></span>

<span data-ttu-id="0302e-113">显示本机应用程序Windows的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="0302e-113">The steps to display the native Windows dialog box are as follows:</span></span>
  
1. <span data-ttu-id="0302e-114">使用 **GetHwnd** Microsoft Excel主Windows句柄。</span><span class="sxs-lookup"><span data-stu-id="0302e-114">Obtain the Microsoft Excel main Windows handle using **GetHwnd**.</span></span>
    
2. <span data-ttu-id="0302e-115">使用 **hookExcelWindow** Excel挂钩主窗口。</span><span class="sxs-lookup"><span data-stu-id="0302e-115">Hook the Excel main window using **HookExcelWindow**.</span></span>
    
3. <span data-ttu-id="0302e-116">使用 **DialogBox 显示对话框**。</span><span class="sxs-lookup"><span data-stu-id="0302e-116">Display the dialog box using **DialogBox**.</span></span>
    
4. <span data-ttu-id="0302e-117">使用 **UnhookExcelWindow** 取消Excel主窗口。</span><span class="sxs-lookup"><span data-stu-id="0302e-117">Unhook the Excel main window using **UnhookExcelWindow**.</span></span>
    
### <a name="example"></a><span data-ttu-id="0302e-118">示例</span><span class="sxs-lookup"><span data-stu-id="0302e-118">Example</span></span>

<span data-ttu-id="0302e-119">有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="0302e-119">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0302e-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0302e-120">See also</span></span>



[<span data-ttu-id="0302e-121">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="0302e-121">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

