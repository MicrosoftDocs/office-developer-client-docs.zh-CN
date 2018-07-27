---
title: xlAutoClose
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoClose
keywords:
- xlautoclose 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 147e46cd-d4d7-49eb-acdc-5a2ebc2fb6c2
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3cbe1cd879fb5a91d14b38f8a659a7f77d943fe7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773846"
---
# <a name="xlautoclose"></a><span data-ttu-id="5c185-104">xlAutoClose</span><span class="sxs-lookup"><span data-stu-id="5c185-104">xlAutoClose</span></span>

 <span data-ttu-id="5c185-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5c185-105">Applies to: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="5c185-106">每当 XLL 停用时由 Microsoft Excel 调用。</span><span class="sxs-lookup"><span data-stu-id="5c185-106">Called by Microsoft Excel whenever the XLL is deactivated.</span></span> <span data-ttu-id="5c185-107">加载项在 Excel 会话正常结束时停用。</span><span class="sxs-lookup"><span data-stu-id="5c185-107">The add-in is deactivated when an Excel session ends normally.</span></span> <span data-ttu-id="5c185-108">加载项可在 Excel 会话期间由用户停用，在这种情况下，将调用此函数。</span><span class="sxs-lookup"><span data-stu-id="5c185-108">The add-in can be deactivated by the user during an Excel session, and this function will be called in that case.</span></span>
  
<span data-ttu-id="5c185-109">Excel 不需要 XLL 实施和导出此函数，尽管建议执行此操作，以便你的 XLL 可以取消注册函数和命令、释放资源、撤销自定义项等。</span><span class="sxs-lookup"><span data-stu-id="5c185-109">Excel does not require an XLL to implement and export this function, although it is advisable so that your XLL can unregister functions and commands, release resources, undo customizations, and so on.</span></span> <span data-ttu-id="5c185-110">如果函数和命令未通过 XLL 显式取消注册，则 Excel 将在调用 **xlAutoClose** 函数后执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5c185-110">If functions and commands are not explicitly unregistered by the XLL, Excel does this after calling the **xlAutoClose** function.</span></span> 
  
```cs
int WINAPI xlAutoClose(void);
```

## <a name="parameters"></a><span data-ttu-id="5c185-111">参数</span><span class="sxs-lookup"><span data-stu-id="5c185-111">Parameters</span></span>

<span data-ttu-id="5c185-112">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="5c185-112">This function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5c185-113">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="5c185-113">Property Value/Return Value</span></span>

<span data-ttu-id="5c185-114">此函数的实现必须返回 1 (**int**)。</span><span class="sxs-lookup"><span data-stu-id="5c185-114">Your implementation of this function must return 1 (**int**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5c185-115">说明</span><span class="sxs-lookup"><span data-stu-id="5c185-115">Remarks</span></span>

<span data-ttu-id="5c185-116">每当 XLL 停用时，Excel 就会调用 **xlAutoClose** 函数，即，从内存中卸载。</span><span class="sxs-lookup"><span data-stu-id="5c185-116">Excel calls the **xlAutoClose** function whenever the XLL is deactivated, that is, unloaded from memory.</span></span> <span data-ttu-id="5c185-117">在以下情况下将停用 XLL：</span><span class="sxs-lookup"><span data-stu-id="5c185-117">The XLL is deactivated in the following situations:</span></span> 
  
- <span data-ttu-id="5c185-118">在 Excel 会话期间的会话正常结束时处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="5c185-118">At the normal end of an Excel session if active during that session.</span></span>
    
- <span data-ttu-id="5c185-119">如果在 Excel 会话过程中显式卸载。</span><span class="sxs-lookup"><span data-stu-id="5c185-119">If explicitly unloaded during an Excel session.</span></span>
    
- <span data-ttu-id="5c185-120">有几种方式可以卸载 XLL：</span><span class="sxs-lookup"><span data-stu-id="5c185-120">An XLL can be unloaded in several ways:</span></span>
    
- <span data-ttu-id="5c185-121">使用加载项管理器。</span><span class="sxs-lookup"><span data-stu-id="5c185-121">Using the Add-In Manager</span></span>
    
- <span data-ttu-id="5c185-122">从调用 [xlfUnregister](xlfunregister-form-1.md) 的另一个 XLL，其中此 DLL 的名称作为唯一参数。</span><span class="sxs-lookup"><span data-stu-id="5c185-122">From another XLL that calls [xlfUnregister](xlfunregister-form-1.md) with the name of this DLL as the only argument.</span></span> 
    
- <span data-ttu-id="5c185-123">从调用 [UNREGISTER](xlfunregister-form-1.md) 的 XLM 宏表，其中此 DLL 的名称作为唯一参数。</span><span class="sxs-lookup"><span data-stu-id="5c185-123">From an XLM macro sheet that calls [UNREGISTER](xlfunregister-form-1.md) with the name of this DLL as the only argument.</span></span> 
    
<span data-ttu-id="5c185-124">此函数应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5c185-124">This function should do the following:</span></span>
  
- <span data-ttu-id="5c185-125">删除由 XLL 添加的任何菜单或菜单项。</span><span class="sxs-lookup"><span data-stu-id="5c185-125">Remove any menus or menu items that were added by the XLL.</span></span>
    
- <span data-ttu-id="5c185-126">执行任何必需的全局清除。</span><span class="sxs-lookup"><span data-stu-id="5c185-126">Perform any necessary global cleanup.</span></span>
    
- <span data-ttu-id="5c185-127">删除已创建的任何名称，尤其是导出的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="5c185-127">Delete any names that were created, especially names of exported functions.</span></span> <span data-ttu-id="5c185-128">请注意，如果 **REGISTER** 的第四个参数存在，则注册函数可能导致创建某些名称。</span><span class="sxs-lookup"><span data-stu-id="5c185-128">Remember that registering functions may cause some names to be created, if the fourth argument to **REGISTER** is present.</span></span> 
    
## <a name="example"></a><span data-ttu-id="5c185-129">示例</span><span class="sxs-lookup"><span data-stu-id="5c185-129">Example</span></span>

<span data-ttu-id="5c185-130">查看文件 `SAMPLES\EXAMPLE\EXAMPLE.C` 和 `SAMPLES\GENERIC\GENERIC.C`，了解此函数的示例实现。</span><span class="sxs-lookup"><span data-stu-id="5c185-130">See the files  `SAMPLES\EXAMPLE\EXAMPLE.C` and  `SAMPLES\GENERIC\GENERIC.C` for example implementations of this function.</span></span> <span data-ttu-id="5c185-131">以下代码来自 `SAMPLES\GENERIC\GENERIC.C`。</span><span class="sxs-lookup"><span data-stu-id="5c185-131">The following code is from  `SAMPLES\GENERIC\GENERIC.C`.</span></span>
  
```cs
int WINAPI xlAutoClose(void)
{
   int i;
   XLOPER12 xRes;
//
// This block first deletes all names added by xlAutoOpen or
// xlAutoRegister12. Next, it checks if the drop-down menu Generic still
// exists. If it does, it is deleted using xlfDeleteMenu. It then checks
// if the Test toolbar still exists. If it is, xlfDeleteToolbar is
// used to delete it.
//
// The following code to delete the defined names
// does not work in the current version of Excel. 
// You cannot delete these names once they are Registered.
// The code is left here in case the functionality becomes 
// available in a future version.
//
   for (i = 0; i < g_rgWorksheetFuncsRows; i++)
      Excel12f(xlfSetName, 0, 1, TempStr12(g_rgWorksheetFuncs[i][2]));
   for (i = 0; i < g_rgCommandFuncsRows; i++)
      Excel12f(xlfSetName, 0, 1, TempStr12(g_rgCommandFuncs[i][2]));
//
// Everything else works as documented.
//
   Excel12f(xlfGetBar, &amp;xRes, 3, TempInt12(10), TempStr12(L"Generic"), TempInt12(0));
   if (xRes.xltype != xltypeErr)
   {
      Excel12f(xlfDeleteMenu, 0, 2, TempNum12(10), TempStr12(L"Generic"));
      // Free the XLOPER12 returned by xlfGetBar //
      Excel12f(xlFree, 0, 1, (LPXLOPER12) &amp;xRes);
   }
   Excel12f(xlfGetToolbar, &amp;xRes, 2, TempInt12(7), TempStr12(L"Test"));
   if (xRes.xltype != xltypeErr)
   {
      Excel12f(xlfDeleteToolbar, 0, 1, TempStr12(L"Test"));
      // Free the XLOPER12 returned by xlfGetToolbar //
      Excel12f(xlFree, 0, 1, (LPXLOPER12) &amp;xRes);
   }
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="5c185-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c185-132">See also</span></span>



[<span data-ttu-id="5c185-133">xlAutoOpen</span><span class="sxs-lookup"><span data-stu-id="5c185-133">xlAutoOpen</span></span>](xlautoopen.md)


[<span data-ttu-id="5c185-134">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="5c185-134">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

