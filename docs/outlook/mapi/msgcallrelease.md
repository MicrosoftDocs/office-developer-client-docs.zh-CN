---
title: MSGCALLRELEASE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MSGCALLRELEASE
api_type:
- COM
ms.assetid: 23c08597-41f0-4f48-a63e-79962fa812bc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9ffaab1e9cc381be2abfb389f4b72067dca2438b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405910"
---
# <a name="msgcallrelease"></a><span data-ttu-id="6f983-103">MSGCALLRELEASE</span><span class="sxs-lookup"><span data-stu-id="6f983-103">MSGCALLRELEASE</span></span>

  
  
<span data-ttu-id="6f983-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f983-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6f983-105">定义一个回调函数, 该函数可以在使用[OpenIMsgOnIStg](openimsgonistg.md)函数的基础之上生成的**IMessage**对象的最终发布后释放**IStorage**接口。</span><span class="sxs-lookup"><span data-stu-id="6f983-105">Defines a callback function that can free an **IStorage** interface after the final release of an **IMessage** object built on top of it with the [OpenIMsgOnIStg](openimsgonistg.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6f983-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6f983-106">Header file:</span></span>  <br/> |<span data-ttu-id="6f983-107">Imessage</span><span class="sxs-lookup"><span data-stu-id="6f983-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="6f983-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="6f983-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="6f983-109">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="6f983-109">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="6f983-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="6f983-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="6f983-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="6f983-111">MAPI</span></span>  <br/> |
   
```cpp
typedef void (STDAPICALLTYPE MSGCALLRELEASE)(
  ULONG  ulCallerData,
  LPMESSAGE  lpMessage );
```

## <a name="parameters"></a><span data-ttu-id="6f983-112">参数</span><span class="sxs-lookup"><span data-stu-id="6f983-112">Parameters</span></span>

 <span data-ttu-id="6f983-113">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="6f983-113">_ulCallerData_</span></span>
  
> <span data-ttu-id="6f983-114">实时包含有关**IMessage**接口的调用应用程序信息。</span><span class="sxs-lookup"><span data-stu-id="6f983-114">[in] Contains calling application information about the **IMessage** interface.</span></span> 
    
 <span data-ttu-id="6f983-115">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="6f983-115">_lpMessage_</span></span>
  
> <span data-ttu-id="6f983-116">实时指向顶级邮件的指针以及已发布的附件。</span><span class="sxs-lookup"><span data-stu-id="6f983-116">[in] Pointer to the top-level message and attachments that have been released.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6f983-117">返回值</span><span class="sxs-lookup"><span data-stu-id="6f983-117">Return value</span></span>

<span data-ttu-id="6f983-118">无。</span><span class="sxs-lookup"><span data-stu-id="6f983-118">None.</span></span>
  

