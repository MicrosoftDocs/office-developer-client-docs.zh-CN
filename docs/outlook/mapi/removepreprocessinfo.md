---
title: RemovePreprocessInfo
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.RemovePreprocessInfo
api_type:
- COM
ms.assetid: 25f46937-abac-4a0b-83db-eeac9451c112
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fab8860621cee5a87b087ee9d98f373baa278e45
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778641"
---
# <a name="removepreprocessinfo"></a><span data-ttu-id="56ee5-103">RemovePreprocessInfo</span><span class="sxs-lookup"><span data-stu-id="56ee5-103">RemovePreprocessInfo</span></span>

  
  
<span data-ttu-id="56ee5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="56ee5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="56ee5-105">删除预处理信息写入由[PreprocessMessage](preprocessmessage.md)基于函数从一条消息。</span><span class="sxs-lookup"><span data-stu-id="56ee5-105">Removes preprocessed information written by a [PreprocessMessage](preprocessmessage.md) based function from a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56ee5-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="56ee5-106">Header file:</span></span>  <br/> |<span data-ttu-id="56ee5-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="56ee5-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="56ee5-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="56ee5-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="56ee5-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="56ee5-109">Transport providers</span></span>  <br/> |
|<span data-ttu-id="56ee5-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="56ee5-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="56ee5-111">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="56ee5-111">MAPI spooler</span></span>  <br/> |
   
```cpp
HRESULT RemovePreprocessInfo(
  LPMESSAGE lpMessage
);
```

## <a name="parameters"></a><span data-ttu-id="56ee5-112">参数</span><span class="sxs-lookup"><span data-stu-id="56ee5-112">Parameters</span></span>

 <span data-ttu-id="56ee5-113">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="56ee5-113">_lpMessage_</span></span>
  
> <span data-ttu-id="56ee5-114">[in]是要移除信息预处理邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="56ee5-114">[in] Pointer to the preprocessed message from which information is to be removed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="56ee5-115">返回值</span><span class="sxs-lookup"><span data-stu-id="56ee5-115">Return value</span></span>

<span data-ttu-id="56ee5-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="56ee5-116">S_OK</span></span>
  
> <span data-ttu-id="56ee5-117">已成功删除预处理的信息。</span><span class="sxs-lookup"><span data-stu-id="56ee5-117">Preprocessed information was removed successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="56ee5-118">说明</span><span class="sxs-lookup"><span data-stu-id="56ee5-118">Remarks</span></span>

<span data-ttu-id="56ee5-119">MAPI 后台处理程序调用基于**RemovePreprocessInfo**函数。</span><span class="sxs-lookup"><span data-stu-id="56ee5-119">The MAPI spooler calls a function based on **RemovePreprocessInfo**.</span></span> <span data-ttu-id="56ee5-120">传输提供程序注册它对[IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法的调用中注册的并行**PreprocessMessage**基于函数的同时**RemovePreprocessInfo**基于函数。</span><span class="sxs-lookup"><span data-stu-id="56ee5-120">A transport provider registers the **RemovePreprocessInfo** based function at the same time it registers the parallel **PreprocessMessage** based function in a call to the [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) method.</span></span> 
  
<span data-ttu-id="56ee5-121">图像呈现适合传真传输是预处理信息由的[PreprocessMessage](preprocessmessage.md)函数原型定义的函数编写的示例。</span><span class="sxs-lookup"><span data-stu-id="56ee5-121">An image rendering suitable for fax transmission is an example of preprocessed information written by a function defined by the [PreprocessMessage](preprocessmessage.md)function prototype.</span></span> <span data-ttu-id="56ee5-122">MAPI 后台处理程序通常发送一条消息，包含预处理的信息后调用**RemovePreprocessInfo**函数。</span><span class="sxs-lookup"><span data-stu-id="56ee5-122">The MAPI spooler usually calls a **RemovePreprocessInfo** function after sending a message that contains preprocessed information.</span></span> 
  

