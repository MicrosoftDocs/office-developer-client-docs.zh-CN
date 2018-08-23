---
title: MapStorageSCode
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MapStorageSCode
api_type:
- COM
ms.assetid: f686a2bc-aba5-4ea3-9963-76d0e96eab50
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8dbb871a234d94f8bb2e21b15ce5de6f0db0e4ee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581830"
---
# <a name="mapstoragescode"></a><span data-ttu-id="1eff7-103">MapStorageSCode</span><span class="sxs-lookup"><span data-stu-id="1eff7-103">MapStorageSCode</span></span>

  
  
<span data-ttu-id="1eff7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1eff7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1eff7-105">地图 SCODE 向 HRESULT 类型返回从 OLE 存储对象的值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-105">Maps an SCODE return value from an OLE storage object to an HRESULT type.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1eff7-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="1eff7-106">Header file:</span></span>  <br/> |<span data-ttu-id="1eff7-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="1eff7-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="1eff7-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="1eff7-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1eff7-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="1eff7-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="1eff7-110">调用：</span><span class="sxs-lookup"><span data-stu-id="1eff7-110">Called by:</span></span>  <br/> |<span data-ttu-id="1eff7-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="1eff7-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE MapStorageSCode(
  SCODE StgSCode
);
```

## <a name="parameters"></a><span data-ttu-id="1eff7-112">参数</span><span class="sxs-lookup"><span data-stu-id="1eff7-112">Parameters</span></span>

 <span data-ttu-id="1eff7-113">_StgSCode_</span><span class="sxs-lookup"><span data-stu-id="1eff7-113">_StgSCode_</span></span>
  
> <span data-ttu-id="1eff7-114">[in]MAPI SCODE 值从 OLE 存储对象返回要映射到 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-114">[in] MAPI SCODE return value from an OLE storage object to be mapped to a HRESULT value.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1eff7-115">返回值</span><span class="sxs-lookup"><span data-stu-id="1eff7-115">Return value</span></span>

<span data-ttu-id="1eff7-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="1eff7-116">S_OK</span></span> 
  
> <span data-ttu-id="1eff7-117">呼叫成功，并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-117">The call succeeded and returned the expected value.</span></span>
    
<span data-ttu-id="1eff7-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="1eff7-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="1eff7-119">该函数找不到匹配值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-119">The function cannot find a matching value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1eff7-120">注解</span><span class="sxs-lookup"><span data-stu-id="1eff7-120">Remarks</span></span>

<span data-ttu-id="1eff7-121">MAPI 内部使用的基础上消息 DLL 其消息实现的 MAPI 组件提供了**MapStorageSCode**函数。</span><span class="sxs-lookup"><span data-stu-id="1eff7-121">MAPI provides the **MapStorageSCode** function for the internal use of MAPI components that base their message implementations on the message DLL.</span></span> <span data-ttu-id="1eff7-122">由于这些组件中打开 OLE 存储本身，它们必须能够映射 HRESULT 值问题与 OLE 存储返回错误值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-122">Because these components open OLE storage themselves, they must be able to map error values returned for problems with OLE storage to an HRESULT value.</span></span> 
  
<span data-ttu-id="1eff7-123">有关详细信息，请参阅[结构化存储文件](structured-storage-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="1eff7-123">For more information, see [Structured Storage](structured-storage-in-mapi.md).</span></span> 
  

