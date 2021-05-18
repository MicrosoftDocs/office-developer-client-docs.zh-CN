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
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: 6583765d4df7c7bfae9e7a62606beaa857874954
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408346"
---
# <a name="ipstoverride1setpersistedregistrations"></a><span data-ttu-id="08e12-103">IPSTOVERRIDE1::SetPersistedRegistrations</span><span class="sxs-lookup"><span data-stu-id="08e12-103">IPSTOVERRIDE1::SetPersistedRegistrations</span></span>

<span data-ttu-id="08e12-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08e12-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08e12-105">将个人文件夹 (.pst) 文件进行自动解锁，以避免进一步调用 HrTrustedPSTOverrideHandlerCallback。</span><span class="sxs-lookup"><span data-stu-id="08e12-105">Registers Personal Folders (.pst) files for automatic unlocking, avoiding further calls to the HrTrustedPSTOverrideHandlerCallback.</span></span>
  
```cpp
HRESULT SetPersistedRegistrations(
  SPropValue *pmval
);
```

## <a name="parameters"></a><span data-ttu-id="08e12-106">参数</span><span class="sxs-lookup"><span data-stu-id="08e12-106">Parameters</span></span>

<span data-ttu-id="08e12-107">_pmval_</span><span class="sxs-lookup"><span data-stu-id="08e12-107">_pmval_</span></span>
  
> <span data-ttu-id="08e12-108">[in]一 [个 SPropValue](spropvalue.md) 结构，包含指向动态链接库路径的指针 (DLL) 进行注册。</span><span class="sxs-lookup"><span data-stu-id="08e12-108">[in] An [SPropValue](spropvalue.md) structure that contains a pointer to the path of the dynamic-link library (DLL) to register.</span></span> <span data-ttu-id="08e12-109">结构具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="08e12-109">The structure has the following characteristics:</span></span> 
    
   - <span data-ttu-id="08e12-110">一个 ulPropTag [](prop_tag.md) PROP_TAG (PT_MV_UNICODE PROP_ID_NULL) 。</span><span class="sxs-lookup"><span data-stu-id="08e12-110">A ulPropTag of [PROP_TAG](prop_tag.md)(PT_MV_UNICODE, PROP_ID_NULL).</span></span>
    
   - <span data-ttu-id="08e12-111">一个 MVszW 值属性，设置为以 null 结束的 Unicode 字符串数组。</span><span class="sxs-lookup"><span data-stu-id="08e12-111">An MVszW value property that is set to an array of null-terminated Unicode character strings.</span></span> <span data-ttu-id="08e12-112">有关详细信息，请参阅 [SWStringArray](swstringarray.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="08e12-112">For more information see the [SWStringArray](swstringarray.md) topic.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="08e12-113">SPropValue 存储在 PST 内部范围的 MAPI 属性中。</span><span class="sxs-lookup"><span data-stu-id="08e12-113">The SPropValue is stored in a MAPI property in the PST's internal range.</span></span> <span data-ttu-id="08e12-114">普通 MAPI 应用程序无法访问此属性。</span><span class="sxs-lookup"><span data-stu-id="08e12-114">This property is inaccessible to ordinary MAPI applications.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="08e12-115">返回值</span><span class="sxs-lookup"><span data-stu-id="08e12-115">Return value</span></span>

<span data-ttu-id="08e12-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="08e12-116">S_OK</span></span> 
  
> <span data-ttu-id="08e12-117">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="08e12-117">The function call was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="08e12-118">备注</span><span class="sxs-lookup"><span data-stu-id="08e12-118">Remarks</span></span>

<span data-ttu-id="08e12-119">保留的注册可能会对打开 PST 的应用程序（如桌面Outlook Windows搜索）的性能产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="08e12-119">Persisted registrations may adversely affect the performance of applications, such as Outlook and Windows Desktop Search, that open PSTs.</span></span> <span data-ttu-id="08e12-120">在使用或扩展持续注册的使用时，请考虑性能影响。</span><span class="sxs-lookup"><span data-stu-id="08e12-120">Consider the performance effect when using or expanding the usage of persisted registrations.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="08e12-121">此方法仅为 Unicode 实现。</span><span class="sxs-lookup"><span data-stu-id="08e12-121">This method is implemented for Unicode only.</span></span> <span data-ttu-id="08e12-122">此外，如果数组中的任一路径的文件扩展名没有扩展名.dll。</span><span class="sxs-lookup"><span data-stu-id="08e12-122">Further, it will preemptively fail if any of the paths in the array do not have a file name extension of .dll.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="08e12-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08e12-123">See also</span></span>

- [<span data-ttu-id="08e12-124">IPSTOVERRIDE1 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08e12-124">IPSTOVERRIDE1 : IUnknown</span></span>](ipstoverride1iunknown.md) 
- [<span data-ttu-id="08e12-125">IPSTOVERRIDEREQ : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08e12-125">IPSTOVERRIDEREQ : IUnknown</span></span>](ipstoverridereqiunknown.md)

