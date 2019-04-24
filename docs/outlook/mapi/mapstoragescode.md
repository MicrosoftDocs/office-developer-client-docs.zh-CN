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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357629"
---
# <a name="mapstoragescode"></a><span data-ttu-id="acbb2-103">MapStorageSCode</span><span class="sxs-lookup"><span data-stu-id="acbb2-103">MapStorageSCode</span></span>

  
  
<span data-ttu-id="acbb2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="acbb2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="acbb2-105">将 SCODE 返回值从 OLE 存储对象映射到 HRESULT 类型。</span><span class="sxs-lookup"><span data-stu-id="acbb2-105">Maps an SCODE return value from an OLE storage object to an HRESULT type.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="acbb2-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="acbb2-106">Header file:</span></span>  <br/> |<span data-ttu-id="acbb2-107">Imessage</span><span class="sxs-lookup"><span data-stu-id="acbb2-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="acbb2-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="acbb2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="acbb2-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="acbb2-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="acbb2-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="acbb2-110">Called by:</span></span>  <br/> |<span data-ttu-id="acbb2-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="acbb2-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE MapStorageSCode(
  SCODE StgSCode
);
```

## <a name="parameters"></a><span data-ttu-id="acbb2-112">参数</span><span class="sxs-lookup"><span data-stu-id="acbb2-112">Parameters</span></span>

 <span data-ttu-id="acbb2-113">_StgSCode_</span><span class="sxs-lookup"><span data-stu-id="acbb2-113">_StgSCode_</span></span>
  
> <span data-ttu-id="acbb2-114">实时MAPI SCODE 从 OLE 存储对象返回要映射到 HRESULT 值的值。</span><span class="sxs-lookup"><span data-stu-id="acbb2-114">[in] MAPI SCODE return value from an OLE storage object to be mapped to a HRESULT value.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="acbb2-115">返回值</span><span class="sxs-lookup"><span data-stu-id="acbb2-115">Return value</span></span>

<span data-ttu-id="acbb2-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="acbb2-116">S_OK</span></span> 
  
> <span data-ttu-id="acbb2-117">调用成功, 并返回所需的值。</span><span class="sxs-lookup"><span data-stu-id="acbb2-117">The call succeeded and returned the expected value.</span></span>
    
<span data-ttu-id="acbb2-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="acbb2-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="acbb2-119">函数找不到匹配的值。</span><span class="sxs-lookup"><span data-stu-id="acbb2-119">The function cannot find a matching value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="acbb2-120">注解</span><span class="sxs-lookup"><span data-stu-id="acbb2-120">Remarks</span></span>

<span data-ttu-id="acbb2-121">mapi 提供了**MapStorageSCode**函数, 用于在邮件 DLL 中基于其邮件实现的 MAPI 组件的内部使用。</span><span class="sxs-lookup"><span data-stu-id="acbb2-121">MAPI provides the **MapStorageSCode** function for the internal use of MAPI components that base their message implementations on the message DLL.</span></span> <span data-ttu-id="acbb2-122">由于这些组件本身打开的是 ole 存储, 因此它们必须能够将 OLE 存储问题返回的错误值映射到 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="acbb2-122">Because these components open OLE storage themselves, they must be able to map error values returned for problems with OLE storage to an HRESULT value.</span></span> 
  
<span data-ttu-id="acbb2-123">有关详细信息, 请参阅[结构化存储](structured-storage-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="acbb2-123">For more information, see [Structured Storage](structured-storage-in-mapi.md).</span></span> 
  

