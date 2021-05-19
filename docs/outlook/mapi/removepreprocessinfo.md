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
ms.openlocfilehash: d80c73aef780a0da39f3939f71462488a067de5f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432945"
---
# <a name="removepreprocessinfo"></a><span data-ttu-id="81275-103">RemovePreprocessInfo</span><span class="sxs-lookup"><span data-stu-id="81275-103">RemovePreprocessInfo</span></span>

  
  
<span data-ttu-id="81275-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81275-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="81275-105">从邮件中删除由基于 [PreprocessMessage](preprocessmessage.md) 的函数写入的预处理信息。</span><span class="sxs-lookup"><span data-stu-id="81275-105">Removes preprocessed information written by a [PreprocessMessage](preprocessmessage.md) based function from a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="81275-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="81275-106">Header file:</span></span>  <br/> |<span data-ttu-id="81275-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="81275-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="81275-108">定义的函数实现方：</span><span class="sxs-lookup"><span data-stu-id="81275-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="81275-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="81275-109">Transport providers</span></span>  <br/> |
|<span data-ttu-id="81275-110">由调用的已定义函数：</span><span class="sxs-lookup"><span data-stu-id="81275-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="81275-111">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="81275-111">MAPI spooler</span></span>  <br/> |
   
```cpp
HRESULT RemovePreprocessInfo(
  LPMESSAGE lpMessage
);
```

## <a name="parameters"></a><span data-ttu-id="81275-112">参数</span><span class="sxs-lookup"><span data-stu-id="81275-112">Parameters</span></span>

 <span data-ttu-id="81275-113">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="81275-113">_lpMessage_</span></span>
  
> <span data-ttu-id="81275-114">[in]指向将从中删除信息的预处理邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="81275-114">[in] Pointer to the preprocessed message from which information is to be removed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="81275-115">返回值</span><span class="sxs-lookup"><span data-stu-id="81275-115">Return value</span></span>

<span data-ttu-id="81275-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="81275-116">S_OK</span></span>
  
> <span data-ttu-id="81275-117">已成功删除预处理的信息。</span><span class="sxs-lookup"><span data-stu-id="81275-117">Preprocessed information was removed successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="81275-118">备注</span><span class="sxs-lookup"><span data-stu-id="81275-118">Remarks</span></span>

<span data-ttu-id="81275-119">MAPI 后台处理程序调用基于 **RemovePreprocessInfo 的函数**。</span><span class="sxs-lookup"><span data-stu-id="81275-119">The MAPI spooler calls a function based on **RemovePreprocessInfo**.</span></span> <span data-ttu-id="81275-120">传输提供程序在注册基于 **RemovePreprocessInfo** 的函数的同时，在 [调用 IMAPISupport：：RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法时注册基于 **PreprocessMessage** 的并行函数。</span><span class="sxs-lookup"><span data-stu-id="81275-120">A transport provider registers the **RemovePreprocessInfo** based function at the same time it registers the parallel **PreprocessMessage** based function in a call to the [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) method.</span></span> 
  
<span data-ttu-id="81275-121">适用于传真传输的图像呈现是由 [PreprocessMessage](preprocessmessage.md)函数原型定义的函数编写的预处理信息的示例。</span><span class="sxs-lookup"><span data-stu-id="81275-121">An image rendering suitable for fax transmission is an example of preprocessed information written by a function defined by the [PreprocessMessage](preprocessmessage.md)function prototype.</span></span> <span data-ttu-id="81275-122">MAPI 后台处理程序通常在发送包含预处理信息的邮件后调用 **RemovePreprocessInfo** 函数。</span><span class="sxs-lookup"><span data-stu-id="81275-122">The MAPI spooler usually calls a **RemovePreprocessInfo** function after sending a message that contains preprocessed information.</span></span> 
  

