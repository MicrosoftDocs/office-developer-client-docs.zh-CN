---
title: RTF_WCSRETINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62561d8d-33cb-e482-7fa0-132afe2b464a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cfa18c215fc98610b836db31e2a07581291910be
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426168"
---
# <a name="rtf_wcsretinfo"></a><span data-ttu-id="f2dd3-103">RTF_WCSRETINFO</span><span class="sxs-lookup"><span data-stu-id="f2dd3-103">RTF_WCSRETINFO</span></span>

<span data-ttu-id="f2dd3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f2dd3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f2dd3-105">此结构提供有关以本机格式返回的流的信息，该流从解压缩以 RTF 格式压缩的 RTF 格式封装的邮件正文 (返回) 。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-105">This structure provides information about a stream in native format returned from decompressing the body of a message that is encapsulated in compressed Rich Text Format (RTF).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="f2dd3-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="f2dd3-106">Quick info</span></span>

```cpp
typedef struct { 
    ULONG size;    
    ULONG ulStreamFlags; 
} RTF_WCSRETINFO;
```

## <a name="members"></a><span data-ttu-id="f2dd3-107">成员</span><span class="sxs-lookup"><span data-stu-id="f2dd3-107">Members</span></span>

<span data-ttu-id="f2dd3-108">_size_</span><span class="sxs-lookup"><span data-stu-id="f2dd3-108">_size_</span></span>
  
> <span data-ttu-id="f2dd3-109">数据库结构 **的大小RTF_WCSRETINFO** 字节数。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-109">The size of the **RTF_WCSRETINFO** structure in number of bytes.</span></span> 
    
<span data-ttu-id="f2dd3-110">_ulStreamFlags_</span><span class="sxs-lookup"><span data-stu-id="f2dd3-110">_ulStreamFlags_</span></span>
  
> <span data-ttu-id="f2dd3-111">此值指示本机正文的格式。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-111">This is a value that indicates the format of the native body.</span></span> <span data-ttu-id="f2dd3-112">只有在传递到 [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的 RTF_WCSINFO 结构的 _ulFlags_ 参数中传递 [MAPI_NATIVE_BODY](rtf_wcsinfo.md)标志时，此值才有效。 </span><span class="sxs-lookup"><span data-stu-id="f2dd3-112">This value is only valid if the **MAPI_NATIVE_BODY** flag is passed in the  _ulFlags_ parameter of the [RTF_WCSINFO](rtf_wcsinfo.md) structure that is passed to the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function.</span></span> <span data-ttu-id="f2dd3-113">这可以是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="f2dd3-113">This can be one of the following values:</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="f2dd3-114">MAPI_NATIVE_BODY_TYPE_RTF</span><span class="sxs-lookup"><span data-stu-id="f2dd3-114">MAPI_NATIVE_BODY_TYPE_RTF</span></span>  <br/> |<span data-ttu-id="f2dd3-115">只有在  _ulFlags_ 包含 MAPI_NATIVE_BODY 标志且正文为 RTF **时** ，才使用此值。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-115">This value is only used if  _ulFlags_ includes the **MAPI_NATIVE_BODY** flag, and the body is RTF.</span></span>  <br/> |
|<span data-ttu-id="f2dd3-116">MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT</span><span class="sxs-lookup"><span data-stu-id="f2dd3-116">MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT</span></span>  <br/> |<span data-ttu-id="f2dd3-117">只有在  _ulFlags_ 包含 MAPI_NATIVE_BODY **标志且** 正文为纯文本格式时，才使用此值。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-117">This value is only used if  _ulFlags_ includes the **MAPI_NATIVE_BODY** flag, and the body is plain text format.</span></span>  <br/> |
|<span data-ttu-id="f2dd3-118">MAPI_NATIVE_BODY_TYPE_HTML</span><span class="sxs-lookup"><span data-stu-id="f2dd3-118">MAPI_NATIVE_BODY_TYPE_HTML</span></span>  <br/> |<span data-ttu-id="f2dd3-119">此值仅在  _ulFlags_ 包括 MAPI_NATIVE_BODY **标志且** 正文为超文本标记语言 (HTML) 使用。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-119">This value is only used if  _ulFlags_ includes the **MAPI_NATIVE_BODY** flag, and the body is Hypertext Markup Language (HTML) format.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f2dd3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2dd3-120">See also</span></span>

- [<span data-ttu-id="f2dd3-121">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="f2dd3-121">WrapCompressedRTFStreamEx</span></span>](wrapcompressedrtfstreamex.md)

