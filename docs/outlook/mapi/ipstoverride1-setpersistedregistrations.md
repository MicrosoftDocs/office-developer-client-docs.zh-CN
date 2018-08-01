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
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 9895c558af94eebebe2dacdb6f9bf674e3de6263
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776056"
---
# <a name="ipstoverride1setpersistedregistrations"></a><span data-ttu-id="b890e-103">IPSTOVERRIDE1::SetPersistedRegistrations</span><span class="sxs-lookup"><span data-stu-id="b890e-103">IPSTOVERRIDE1::SetPersistedRegistrations</span></span>

<span data-ttu-id="b890e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b890e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b890e-105">避免进一步调用 HrTrustedPSTOverrideHandlerCallback 注册自动解锁个人文件夹 (.pst) 文件。</span><span class="sxs-lookup"><span data-stu-id="b890e-105">Registers Personal Folders (.pst) files for automatic unlocking, avoiding further calls to the HrTrustedPSTOverrideHandlerCallback.</span></span>
  
```cpp
HRESULT SetPersistedRegistrations(
  SPropValue *pmval
);
```

## <a name="parameters"></a><span data-ttu-id="b890e-106">参数</span><span class="sxs-lookup"><span data-stu-id="b890e-106">Parameters</span></span>

<span data-ttu-id="b890e-107">_pmval_</span><span class="sxs-lookup"><span data-stu-id="b890e-107">_pmval_</span></span>
  
> <span data-ttu-id="b890e-108">[in][SPropValue](spropvalue.md)结构，其中包含一个指向动态链接库 (DLL) 注册的路径。</span><span class="sxs-lookup"><span data-stu-id="b890e-108">[in] An [SPropValue](spropvalue.md) structure that contains a pointer to the path of the dynamic-link library (DLL) to register.</span></span> <span data-ttu-id="b890e-109">结构具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="b890e-109">The structure has the following characteristics:</span></span> 
    
   - <span data-ttu-id="b890e-110">[PROP_TAG](prop_tag.md)（PT_MV_UNICODE、 PROP_ID_NULL） ulPropTag。</span><span class="sxs-lookup"><span data-stu-id="b890e-110">A ulPropTag of [PROP_TAG](prop_tag.md)(PT_MV_UNICODE, PROP_ID_NULL).</span></span>
    
   - <span data-ttu-id="b890e-111">设置为 null 结尾的 Unicode 字符字符串数组 MVszW value 属性。</span><span class="sxs-lookup"><span data-stu-id="b890e-111">An MVszW value property that is set to an array of null-terminated Unicode character strings.</span></span> <span data-ttu-id="b890e-112">有关详细信息，请参阅[SWStringArray](swstringarray.md)主题。</span><span class="sxs-lookup"><span data-stu-id="b890e-112">For more information see the [SWStringArray](swstringarray.md) topic.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b890e-113">SPropValue 存储在 PST 的内部区域中的 MAPI 属性中。</span><span class="sxs-lookup"><span data-stu-id="b890e-113">The SPropValue is stored in a MAPI property in the PST's internal range.</span></span> <span data-ttu-id="b890e-114">此属性为普通的 MAPI 应用程序无法访问。</span><span class="sxs-lookup"><span data-stu-id="b890e-114">This property is inaccessible to ordinary MAPI applications.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="b890e-115">返回值</span><span class="sxs-lookup"><span data-stu-id="b890e-115">Return value</span></span>

<span data-ttu-id="b890e-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b890e-116">S_OK</span></span> 
  
> <span data-ttu-id="b890e-117">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="b890e-117">The function call was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b890e-118">说明</span><span class="sxs-lookup"><span data-stu-id="b890e-118">Remarks</span></span>

<span data-ttu-id="b890e-119">持久化的注册可能会影响应用程序的性能，如 Outlook 和 Windows 桌面搜索，打开 Pst 的。</span><span class="sxs-lookup"><span data-stu-id="b890e-119">Persisted registrations may adversely affect the performance of applications, such as Outlook and Windows Desktop Search, that open PSTs.</span></span> <span data-ttu-id="b890e-120">请考虑使用或展开持久化注册的使用情况时的性能影响。</span><span class="sxs-lookup"><span data-stu-id="b890e-120">Consider the performance effect when using or expanding the usage of persisted registrations.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b890e-121">此方法仅实现为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="b890e-121">This method is implemented for Unicode only.</span></span> <span data-ttu-id="b890e-122">此外，它将预先失败如果任何路径数组中没有的.dll 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="b890e-122">Further, it will preemptively fail if any of the paths in the array do not have a file name extension of .dll.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b890e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b890e-123">See also</span></span>

- [<span data-ttu-id="b890e-124">IPSTOVERRIDE1 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b890e-124">IPSTOVERRIDE1 : IUnknown</span></span>](ipstoverride1iunknown.md) 
- [<span data-ttu-id="b890e-125">IPSTOVERRIDEREQ : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b890e-125">IPSTOVERRIDEREQ : IUnknown</span></span>](ipstoverridereqiunknown.md)

