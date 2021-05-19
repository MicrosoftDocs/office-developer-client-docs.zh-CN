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
ms.openlocfilehash: 5dce5de820c07e1fa7b25b87d87993a30961b3f2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416522"
---
# <a name="mapstoragescode"></a><span data-ttu-id="edfe8-103">MapStorageSCode</span><span class="sxs-lookup"><span data-stu-id="edfe8-103">MapStorageSCode</span></span>

  
  
<span data-ttu-id="edfe8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="edfe8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="edfe8-105">地图 OLE 存储对象向 HRESULT 类型返回 SCODE 返回值。</span><span class="sxs-lookup"><span data-stu-id="edfe8-105">Maps an SCODE return value from an OLE storage object to an HRESULT type.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="edfe8-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="edfe8-106">Header file:</span></span>  <br/> |<span data-ttu-id="edfe8-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="edfe8-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="edfe8-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="edfe8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="edfe8-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="edfe8-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="edfe8-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="edfe8-110">Called by:</span></span>  <br/> |<span data-ttu-id="edfe8-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="edfe8-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE MapStorageSCode(
  SCODE StgSCode
);
```

## <a name="parameters"></a><span data-ttu-id="edfe8-112">参数</span><span class="sxs-lookup"><span data-stu-id="edfe8-112">Parameters</span></span>

 <span data-ttu-id="edfe8-113">_StgSCode_</span><span class="sxs-lookup"><span data-stu-id="edfe8-113">_StgSCode_</span></span>
  
> <span data-ttu-id="edfe8-114">[in]MAPI SCODE 返回要映射到 HRESULT 值的 OLE 存储对象中的值。</span><span class="sxs-lookup"><span data-stu-id="edfe8-114">[in] MAPI SCODE return value from an OLE storage object to be mapped to a HRESULT value.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="edfe8-115">返回值</span><span class="sxs-lookup"><span data-stu-id="edfe8-115">Return value</span></span>

<span data-ttu-id="edfe8-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="edfe8-116">S_OK</span></span> 
  
> <span data-ttu-id="edfe8-117">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="edfe8-117">The call succeeded and returned the expected value.</span></span>
    
<span data-ttu-id="edfe8-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="edfe8-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="edfe8-119">函数找不到匹配值。</span><span class="sxs-lookup"><span data-stu-id="edfe8-119">The function cannot find a matching value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="edfe8-120">备注</span><span class="sxs-lookup"><span data-stu-id="edfe8-120">Remarks</span></span>

<span data-ttu-id="edfe8-121">MAPI 提供 **MapStorageSCode** 函数，供内部使用 MAPI 组件，这些组件基于消息 DLL 实现其邮件实现。</span><span class="sxs-lookup"><span data-stu-id="edfe8-121">MAPI provides the **MapStorageSCode** function for the internal use of MAPI components that base their message implementations on the message DLL.</span></span> <span data-ttu-id="edfe8-122">因为这些组件自行打开 OLE 存储，所以它们必须能够将针对 OLE 存储问题返回的错误值映射到 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="edfe8-122">Because these components open OLE storage themselves, they must be able to map error values returned for problems with OLE storage to an HRESULT value.</span></span> 
  
<span data-ttu-id="edfe8-123">有关详细信息，请参阅结构化[存储。](structured-storage-in-mapi.md)</span><span class="sxs-lookup"><span data-stu-id="edfe8-123">For more information, see [Structured Storage](structured-storage-in-mapi.md).</span></span> 
  

