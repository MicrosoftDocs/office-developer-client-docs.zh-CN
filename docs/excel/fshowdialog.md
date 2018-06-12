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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: ae6d8b2f0b95641678947e9bd75daa2237b080b1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773758"
---
# <a name="fshowdialog"></a><span data-ttu-id="3368c-104">fShowDialog</span><span class="sxs-lookup"><span data-stu-id="3368c-104">fShowDialog</span></span>

 <span data-ttu-id="3368c-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3368c-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="3368c-106">示例用户定义的命令，加载和显示示例本机 Windows 的对话框。</span><span class="sxs-lookup"><span data-stu-id="3368c-106">Example user-defined command that loads and displays an example native Windows dialog box.</span></span> <span data-ttu-id="3368c-107">当加载 GENERIC.xll 时，它会创建用户定义的菜单中，一般，通过其访问此命令。</span><span class="sxs-lookup"><span data-stu-id="3368c-107">When GENERIC.xll is loaded, it creates a user-defined menu, Generic, through which this command is accessed.</span></span>
  
```cs
int WINAPI fShowDialog(void);
```

## <a name="parameters"></a><span data-ttu-id="3368c-108">参数</span><span class="sxs-lookup"><span data-stu-id="3368c-108">Parameters</span></span>

<span data-ttu-id="3368c-109">函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="3368c-109">The function takes no parameters.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3368c-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="3368c-110">Property value/Return value</span></span>

<span data-ttu-id="3368c-111">函数返回整数零指示成功完成</span><span class="sxs-lookup"><span data-stu-id="3368c-111">The function return integer zero to indicate successful completion</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3368c-112">备注</span><span class="sxs-lookup"><span data-stu-id="3368c-112">Remarks</span></span>

<span data-ttu-id="3368c-113">显示本机 Windows 对话框中的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="3368c-113">The steps to display the native Windows dialog box are as follows:</span></span>
  
1. <span data-ttu-id="3368c-114">获取使用**GetHwnd**的 Microsoft Excel 主窗口句。</span><span class="sxs-lookup"><span data-stu-id="3368c-114">Obtain the Microsoft Excel main Windows handle using **GetHwnd**.</span></span>
    
2. <span data-ttu-id="3368c-115">挂接使用**HookExcelWindow**Excel 主窗口。</span><span class="sxs-lookup"><span data-stu-id="3368c-115">Hook the Excel main window using **HookExcelWindow**.</span></span>
    
3. <span data-ttu-id="3368c-116">显示使用**DialogBox**对话框。</span><span class="sxs-lookup"><span data-stu-id="3368c-116">Display the dialog box using **DialogBox**.</span></span>
    
4. <span data-ttu-id="3368c-117">打开 Excel 主窗口中使用**UnhookExcelWindow**闩锁。</span><span class="sxs-lookup"><span data-stu-id="3368c-117">Unhook the Excel main window using **UnhookExcelWindow**.</span></span>
    
### <a name="example"></a><span data-ttu-id="3368c-118">示例</span><span class="sxs-lookup"><span data-stu-id="3368c-118">Example</span></span>

<span data-ttu-id="3368c-119">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="3368c-119">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3368c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3368c-120">See also</span></span>



[<span data-ttu-id="3368c-121">泛型 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="3368c-121">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

