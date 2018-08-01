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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e4bce7f122522532023d18b43fe4bfdeda84af9b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774914"
---
# <a name="fgetcomponentpath"></a><span data-ttu-id="32f82-103">FGetComponentPath</span><span class="sxs-lookup"><span data-stu-id="32f82-103">FGetComponentPath</span></span>

  
  
<span data-ttu-id="32f82-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="32f82-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="32f82-105">返回专用 Mapi32.dll 的路径。</span><span class="sxs-lookup"><span data-stu-id="32f82-105">Returns the path to the private Mapi32.dll.</span></span>
  
```cpp
BOOL FGetComponentPath(
  LPCSTR szComponent,
  LPSTR szQualifier,
  LPSTR szDllPath,
  DWORD cchBufferSize,
  BOOL fInstall
);
```

## <a name="parameters"></a><span data-ttu-id="32f82-106">参数</span><span class="sxs-lookup"><span data-stu-id="32f82-106">Parameters</span></span>

 <span data-ttu-id="32f82-107">_szComponent_</span><span class="sxs-lookup"><span data-stu-id="32f82-107">_szComponent_</span></span>
  
> <span data-ttu-id="32f82-108">[in]MSIComponentID 注册表项[Mapi32.dll 存根注册表 Settings](http://msdn.microsoft.com/en-us/library/dd162409.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="32f82-108">[in] The MSIComponentID reg key described in [Mapi32.dll Stub Registry Settings](http://msdn.microsoft.com/en-us/library/dd162409.aspx).</span></span>
    
 <span data-ttu-id="32f82-109">_szQualifier_</span><span class="sxs-lookup"><span data-stu-id="32f82-109">_szQualifier_</span></span>
  
> <span data-ttu-id="32f82-110">[in][选择特定版本的 MAPI 到负载](how-to-choose-a-specific-version-of-mapi-to-load.md)中描述的 MSIApplicationLCID 或 MSIOfficeLCID 子项。</span><span class="sxs-lookup"><span data-stu-id="32f82-110">[in] The MSIApplicationLCID or MSIOfficeLCID subkey described in [Choose a Specific Version of MAPI to Load](how-to-choose-a-specific-version-of-mapi-to-load.md).</span></span> <span data-ttu-id="32f82-111">如果没有任何限定符，调用方可以传递**null** 。</span><span class="sxs-lookup"><span data-stu-id="32f82-111">Callers can pass **null** if there is no qualifier.</span></span> 
    
 <span data-ttu-id="32f82-112">_szDllPath_</span><span class="sxs-lookup"><span data-stu-id="32f82-112">_szDllPath_</span></span>
  
> <span data-ttu-id="32f82-113">[in]指向专用 Mapi32.dll，已完整 MAPI 功能 （作为 Mapi32.dll 相同的导出） 的路径。</span><span class="sxs-lookup"><span data-stu-id="32f82-113">[in] The path to the private Mapi32.dll, which has full MAPI functionality (the same exports as the Mapi32.dll).</span></span>
    
 <span data-ttu-id="32f82-114">_cchBufferSize_</span><span class="sxs-lookup"><span data-stu-id="32f82-114">_cchBufferSize_</span></span>
  
> <span data-ttu-id="32f82-115">[in]_SzDllPath_，以字符为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="32f82-115">[in] The size of  _szDllPath_, in characters.</span></span>
    
 <span data-ttu-id="32f82-116">_fInstall_</span><span class="sxs-lookup"><span data-stu-id="32f82-116">_fInstall_</span></span>
  
> <span data-ttu-id="32f82-117">[in]告知 MAPI 安装私有 Mapi32.dll 组件，如果不存在。</span><span class="sxs-lookup"><span data-stu-id="32f82-117">[in] Tells MAPI to install the private Mapi32.dll component if it is absent.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="32f82-118">返回值</span><span class="sxs-lookup"><span data-stu-id="32f82-118">Return value</span></span>

 <span data-ttu-id="32f82-119">**true**</span><span class="sxs-lookup"><span data-stu-id="32f82-119">**true**</span></span>
  
> <span data-ttu-id="32f82-120">找到路径。</span><span class="sxs-lookup"><span data-stu-id="32f82-120">The path was found.</span></span>
    
 <span data-ttu-id="32f82-121">**false**</span><span class="sxs-lookup"><span data-stu-id="32f82-121">**false**</span></span>
  
> <span data-ttu-id="32f82-122">找不到路径。</span><span class="sxs-lookup"><span data-stu-id="32f82-122">The path was not found.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="32f82-123">说明</span><span class="sxs-lookup"><span data-stu-id="32f82-123">Remarks</span></span>

<span data-ttu-id="32f82-124">当您需要获取专用 Mapi32.dll 的路径，请使用**FGetComponentPath**函数。</span><span class="sxs-lookup"><span data-stu-id="32f82-124">Use the **FGetComponentPath** function when you need to get the path to the private Mapi32.dll.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="32f82-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32f82-125">See also</span></span>



[<span data-ttu-id="32f82-126">选择要加载的 MAPI 的特定版本</span><span class="sxs-lookup"><span data-stu-id="32f82-126">Choose a Specific Version of MAPI to Load</span></span>](how-to-choose-a-specific-version-of-mapi-to-load.md)


[<span data-ttu-id="32f82-127">Mapi32.dll 存根注册表设置</span><span class="sxs-lookup"><span data-stu-id="32f82-127">Mapi32.dll Stub Registry Settings</span></span>](http://msdn.microsoft.com/en-us/library/dd162409.aspx)

