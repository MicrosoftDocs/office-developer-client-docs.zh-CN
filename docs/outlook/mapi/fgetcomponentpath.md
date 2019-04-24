---
title: FGetComponentPath
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FGetComponentPath
api_type:
- COM
ms.assetid: 2a303458-3283-409a-bc3b-b891f3fcfc22
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3456d81935a0a94bc2158eefd321da968dda9983
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335208"
---
# <a name="fgetcomponentpath"></a><span data-ttu-id="594ef-103">FGetComponentPath</span><span class="sxs-lookup"><span data-stu-id="594ef-103">FGetComponentPath</span></span>

  
  
<span data-ttu-id="594ef-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="594ef-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="594ef-105">返回私有 Mapi32 的路径。</span><span class="sxs-lookup"><span data-stu-id="594ef-105">Returns the path to the private Mapi32.dll.</span></span>
  
```cpp
BOOL FGetComponentPath(
  LPCSTR szComponent,
  LPSTR szQualifier,
  LPSTR szDllPath,
  DWORD cchBufferSize,
  BOOL fInstall
);
```

## <a name="parameters"></a><span data-ttu-id="594ef-106">参数</span><span class="sxs-lookup"><span data-stu-id="594ef-106">Parameters</span></span>

 <span data-ttu-id="594ef-107">_szComponent_</span><span class="sxs-lookup"><span data-stu-id="594ef-107">_szComponent_</span></span>
  
> <span data-ttu-id="594ef-108">实时[Mapi32 存根 (Stub) 注册表设置](https://msdn.microsoft.com/library/dd162409.aspx)中所述的 MSIComponentID 注册表项。</span><span class="sxs-lookup"><span data-stu-id="594ef-108">[in] The MSIComponentID reg key described in [Mapi32.dll Stub Registry Settings](https://msdn.microsoft.com/library/dd162409.aspx).</span></span>
    
 <span data-ttu-id="594ef-109">_szQualifier_</span><span class="sxs-lookup"><span data-stu-id="594ef-109">_szQualifier_</span></span>
  
> <span data-ttu-id="594ef-110">实时[选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)中所述的 MSIApplicationLCID 或 MSIOfficeLCID 子项。</span><span class="sxs-lookup"><span data-stu-id="594ef-110">[in] The MSIApplicationLCID or MSIOfficeLCID subkey described in [Choose a Specific Version of MAPI to Load](how-to-choose-a-specific-version-of-mapi-to-load.md).</span></span> <span data-ttu-id="594ef-111">如果没有限定符, 调用方可以传递**null** 。</span><span class="sxs-lookup"><span data-stu-id="594ef-111">Callers can pass **null** if there is no qualifier.</span></span> 
    
 <span data-ttu-id="594ef-112">_szDllPath_</span><span class="sxs-lookup"><span data-stu-id="594ef-112">_szDllPath_</span></span>
  
> <span data-ttu-id="594ef-113">实时包含完整 MAPI 功能 (与 Mapi32 相同的导出) 的专用 Mapi32 的路径。</span><span class="sxs-lookup"><span data-stu-id="594ef-113">[in] The path to the private Mapi32.dll, which has full MAPI functionality (the same exports as the Mapi32.dll).</span></span>
    
 <span data-ttu-id="594ef-114">_cchBufferSize_</span><span class="sxs-lookup"><span data-stu-id="594ef-114">_cchBufferSize_</span></span>
  
> <span data-ttu-id="594ef-115">实时_szDllPath_的大小, 以字符为单位。</span><span class="sxs-lookup"><span data-stu-id="594ef-115">[in] The size of  _szDllPath_, in characters.</span></span>
    
 <span data-ttu-id="594ef-116">_fInstall_</span><span class="sxs-lookup"><span data-stu-id="594ef-116">_fInstall_</span></span>
  
> <span data-ttu-id="594ef-117">实时通知 MAPI 安装私有 Mapi32 组件 (如果缺少)。</span><span class="sxs-lookup"><span data-stu-id="594ef-117">[in] Tells MAPI to install the private Mapi32.dll component if it is absent.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="594ef-118">返回值</span><span class="sxs-lookup"><span data-stu-id="594ef-118">Return value</span></span>

 <span data-ttu-id="594ef-119">**true**</span><span class="sxs-lookup"><span data-stu-id="594ef-119">**true**</span></span>
  
> <span data-ttu-id="594ef-120">找到路径。</span><span class="sxs-lookup"><span data-stu-id="594ef-120">The path was found.</span></span>
    
 <span data-ttu-id="594ef-121">**该值**</span><span class="sxs-lookup"><span data-stu-id="594ef-121">**false**</span></span>
  
> <span data-ttu-id="594ef-122">找不到路径。</span><span class="sxs-lookup"><span data-stu-id="594ef-122">The path was not found.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="594ef-123">注解</span><span class="sxs-lookup"><span data-stu-id="594ef-123">Remarks</span></span>

<span data-ttu-id="594ef-124">当您需要获取专用 Mapi32 的路径时, 请使用**FGetComponentPath**函数。</span><span class="sxs-lookup"><span data-stu-id="594ef-124">Use the **FGetComponentPath** function when you need to get the path to the private Mapi32.dll.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="594ef-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="594ef-125">See also</span></span>



[<span data-ttu-id="594ef-126">选择要加载的 MAPI 的特定版本</span><span class="sxs-lookup"><span data-stu-id="594ef-126">Choose a Specific Version of MAPI to Load</span></span>](how-to-choose-a-specific-version-of-mapi-to-load.md)


[<span data-ttu-id="594ef-127">Mapi32 存根注册表设置</span><span class="sxs-lookup"><span data-stu-id="594ef-127">Mapi32.dll Stub Registry Settings</span></span>](https://msdn.microsoft.com/library/dd162409.aspx)

