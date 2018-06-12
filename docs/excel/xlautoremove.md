---
title: xlAutoRemove
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoRemove
keywords:
- xlautoremove 函数 [excel 2007]
localization_priority: Normal
ms.assetid: fff0de4d-605d-49e6-a5be-a000410c09d8
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 6e5daac21a6d89472a7d84a25e9aeaea56db1ae1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773843"
---
# <a name="xlautoremove"></a><span data-ttu-id="3644d-104">xlAutoRemove</span><span class="sxs-lookup"><span data-stu-id="3644d-104">xlAutoRemove</span></span>

 <span data-ttu-id="3644d-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3644d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="3644d-106">由 Microsoft Excel 每当用户将停用 XLL Excel 会话过程中使用加载项管理器调用。</span><span class="sxs-lookup"><span data-stu-id="3644d-106">Called by Microsoft Excel whenever the user deactivates the XLL during an Excel session by using the Add-In Manager.</span></span> <span data-ttu-id="3644d-107">Excel 关闭会话时，通常或异常，与安装的加载项时，不会调用此函数。</span><span class="sxs-lookup"><span data-stu-id="3644d-107">This function is not called when an Excel session closes, normally or abnormally, with the add-in installed.</span></span>
  
<span data-ttu-id="3644d-108">可以使用此函数，以显示自定义对话框告知用户的外接程序已停用，或进行读取或写入到注册表，例如。</span><span class="sxs-lookup"><span data-stu-id="3644d-108">This function can be used to display a custom dialog box telling the user that the add-in has been deactivated, or to read from or write to the registry, for example.</span></span>
  
<span data-ttu-id="3644d-109">Excel 不需要 XLL 实施和导出此函数。</span><span class="sxs-lookup"><span data-stu-id="3644d-109">Excel does not require an XLL to implement and export this function.</span></span> 
  
```cs
int WINAPI xlAutoRemove(void);
```

## <a name="parameters"></a><span data-ttu-id="3644d-110">参数</span><span class="sxs-lookup"><span data-stu-id="3644d-110">Parameters</span></span>

<span data-ttu-id="3644d-111">此函数不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="3644d-111">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3644d-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="3644d-112">Property value/Return value</span></span>

<span data-ttu-id="3644d-113">此函数的实现必须返回 1 (**int**)。</span><span class="sxs-lookup"><span data-stu-id="3644d-113">Your implementation of this function must return 1 (**int**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3644d-114">备注</span><span class="sxs-lookup"><span data-stu-id="3644d-114">Remarks</span></span>

<span data-ttu-id="3644d-115">如果您 XLL 需要完成任何任务加载项管理器中删除时，请使用此函数。</span><span class="sxs-lookup"><span data-stu-id="3644d-115">Use this function if your XLL needs to complete any task when it is removed by the Add-In Manager.</span></span>
  
## <a name="example"></a><span data-ttu-id="3644d-116">示例</span><span class="sxs-lookup"><span data-stu-id="3644d-116">Example</span></span>

<span data-ttu-id="3644d-117">请参阅文件`\SAMPLES\EXAMPLE\EXAMPLE.C`和`\SAMPLES\GENERIC\GENERIC.C`，例如此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="3644d-117">See the files  `\SAMPLES\EXAMPLE\EXAMPLE.C` and  `\SAMPLES\GENERIC\GENERIC.C` for example implementations of this function.</span></span> <span data-ttu-id="3644d-118">下面的代码是从`\SAMPLES\EXAMPLE\EXAMPLE.C`。</span><span class="sxs-lookup"><span data-stu-id="3644d-118">The following code is from  `\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span>
  
```cs
int WINAPI xlAutoRemove(void)
{
/* Display a dialog box indicating that the XLL was successfully removed */
   Excel12f(xlcAlert, 0, 2,
      TempStr12(L"Thank you for removing Example.XLL!"),
      TempInt12(2));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="3644d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3644d-119">See also</span></span>



[<span data-ttu-id="3644d-120">xlAutoAdd</span><span class="sxs-lookup"><span data-stu-id="3644d-120">xlAutoAdd</span></span>](xlautoadd.md)


[<span data-ttu-id="3644d-121">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="3644d-121">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

