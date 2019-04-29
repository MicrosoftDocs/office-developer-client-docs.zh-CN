---
title: IPSTOVERRIDE1SetPersistedRegistrations
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDE1.SetPersistedRegistrations
api_type:
- COM
ms.assetid: 5f4b62db-a759-41a2-9bea-29fc04b2962b
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: 6583765d4df7c7bfae9e7a62606beaa857874954
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408346"
---
# <a name="ipstoverride1setpersistedregistrations"></a><span data-ttu-id="65fc3-103">IPSTOVERRIDE1::SetPersistedRegistrations</span><span class="sxs-lookup"><span data-stu-id="65fc3-103">IPSTOVERRIDE1::SetPersistedRegistrations</span></span>

<span data-ttu-id="65fc3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65fc3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65fc3-105">为自动解锁注册个人文件夹 (.pst) 文件, 以避免对 HrTrustedPSTOverrideHandlerCallback 的进一步调用。</span><span class="sxs-lookup"><span data-stu-id="65fc3-105">Registers Personal Folders (.pst) files for automatic unlocking, avoiding further calls to the HrTrustedPSTOverrideHandlerCallback.</span></span>
  
```cpp
HRESULT SetPersistedRegistrations(
  SPropValue *pmval
);
```

## <a name="parameters"></a><span data-ttu-id="65fc3-106">参数</span><span class="sxs-lookup"><span data-stu-id="65fc3-106">Parameters</span></span>

<span data-ttu-id="65fc3-107">_pmval_</span><span class="sxs-lookup"><span data-stu-id="65fc3-107">_pmval_</span></span>
  
> <span data-ttu-id="65fc3-108">实时一个[SPropValue](spropvalue.md)结构, 其中包含指向要注册的动态链接库 (DLL) 的路径的指针。</span><span class="sxs-lookup"><span data-stu-id="65fc3-108">[in] An [SPropValue](spropvalue.md) structure that contains a pointer to the path of the dynamic-link library (DLL) to register.</span></span> <span data-ttu-id="65fc3-109">结构具有以下特征:</span><span class="sxs-lookup"><span data-stu-id="65fc3-109">The structure has the following characteristics:</span></span> 
    
   - <span data-ttu-id="65fc3-110">[PROP_TAG](prop_tag.md)(PT_MV_UNICODE, PROP_ID_NULL) 的 ulPropTag。</span><span class="sxs-lookup"><span data-stu-id="65fc3-110">A ulPropTag of [PROP_TAG](prop_tag.md)(PT_MV_UNICODE, PROP_ID_NULL).</span></span>
    
   - <span data-ttu-id="65fc3-111">一个 MVszW 值属性, 该属性设置为以 null 结尾的 Unicode 字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="65fc3-111">An MVszW value property that is set to an array of null-terminated Unicode character strings.</span></span> <span data-ttu-id="65fc3-112">有关详细信息, 请参阅[SWStringArray](swstringarray.md)主题。</span><span class="sxs-lookup"><span data-stu-id="65fc3-112">For more information see the [SWStringArray](swstringarray.md) topic.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="65fc3-113">SPropValue 存储在 PST 的内部范围内的 MAPI 属性中。</span><span class="sxs-lookup"><span data-stu-id="65fc3-113">The SPropValue is stored in a MAPI property in the PST's internal range.</span></span> <span data-ttu-id="65fc3-114">普通 MAPI 应用程序无法访问此属性。</span><span class="sxs-lookup"><span data-stu-id="65fc3-114">This property is inaccessible to ordinary MAPI applications.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="65fc3-115">返回值</span><span class="sxs-lookup"><span data-stu-id="65fc3-115">Return value</span></span>

<span data-ttu-id="65fc3-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="65fc3-116">S_OK</span></span> 
  
> <span data-ttu-id="65fc3-117">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="65fc3-117">The function call was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="65fc3-118">说明</span><span class="sxs-lookup"><span data-stu-id="65fc3-118">Remarks</span></span>

<span data-ttu-id="65fc3-119">持久化注册可能会对打开 pst 的应用程序 (如 Outlook 和 Windows 桌面搜索) 的性能产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="65fc3-119">Persisted registrations may adversely affect the performance of applications, such as Outlook and Windows Desktop Search, that open PSTs.</span></span> <span data-ttu-id="65fc3-120">在使用或扩展持久化注册的使用情况时, 请考虑性能影响。</span><span class="sxs-lookup"><span data-stu-id="65fc3-120">Consider the performance effect when using or expanding the usage of persisted registrations.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="65fc3-121">仅为 Unicode 实现此方法。</span><span class="sxs-lookup"><span data-stu-id="65fc3-121">This method is implemented for Unicode only.</span></span> <span data-ttu-id="65fc3-122">此外, 如果数组中的任何路径的文件扩展名均不为 .dll, 则 preemptively 将失败。</span><span class="sxs-lookup"><span data-stu-id="65fc3-122">Further, it will preemptively fail if any of the paths in the array do not have a file name extension of .dll.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="65fc3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65fc3-123">See also</span></span>

- [<span data-ttu-id="65fc3-124">IPSTOVERRIDE1 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="65fc3-124">IPSTOVERRIDE1 : IUnknown</span></span>](ipstoverride1iunknown.md) 
- [<span data-ttu-id="65fc3-125">IPSTOVERRIDEREQ : IUnknown</span><span class="sxs-lookup"><span data-stu-id="65fc3-125">IPSTOVERRIDEREQ : IUnknown</span></span>](ipstoverridereqiunknown.md)

