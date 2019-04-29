---
title: RTF_WCSINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0c94501e-0ec7-e836-33a7-adcf5a61b375
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6bec29aa0e88e0224f9cd6049553f2df6379e23d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430530"
---
# <a name="rtfwcsinfo"></a><span data-ttu-id="ef2a4-103">RTF_WCSINFO</span><span class="sxs-lookup"><span data-stu-id="ef2a4-103">RTF_WCSINFO</span></span>

  
  
<span data-ttu-id="ef2a4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ef2a4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ef2a4-105">通过此结构, 您可以指定信息以压缩的 rtf 格式 (rtf) 解压缩邮件正文, 也可以选择以本机格式返回正文流。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-105">This structure enables you to specify information to decompress the body of a message in compressed Rich Text Format (RTF) and, optionally, return the body stream in its native format.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="ef2a4-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="ef2a4-106">Quick info</span></span>

```cpp
typedef struct { 
    ULONG size; 
    ULONG ulFlags; 
    ULONG ulInCodePage; 
    ULONG ulOutCodePage; 
} RTF_WCSINFO;

```

## <a name="members"></a><span data-ttu-id="ef2a4-107">成员</span><span class="sxs-lookup"><span data-stu-id="ef2a4-107">Members</span></span>

 <span data-ttu-id="ef2a4-108">_size_</span><span class="sxs-lookup"><span data-stu-id="ef2a4-108">_size_</span></span>
  
> <span data-ttu-id="ef2a4-109">以字节数表示的**RTF_WCSINFO**结构的大小。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-109">The size of the **RTF_WCSINFO** structure in number of bytes.</span></span> 
    
 <span data-ttu-id="ef2a4-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ef2a4-110">_ulFlags_</span></span>
  
> <span data-ttu-id="ef2a4-111">这是[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的选项标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-111">This is the bitmask of option flags for the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function.</span></span> <span data-ttu-id="ef2a4-112">受支持的选项标志为:</span><span class="sxs-lookup"><span data-stu-id="ef2a4-112">The supported option flags are:</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="ef2a4-113">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="ef2a4-113">MAPI_MODIFY</span></span>  <br/> |<span data-ttu-id="ef2a4-114">这指示客户端是否打算写入已返回的包装流接口。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-114">This indicates whether the client intends to write the wrapped stream interface that is returned.</span></span>  <br/> |
|<span data-ttu-id="ef2a4-115">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="ef2a4-115">STORE_UNCOMPRESSED_RTF</span></span>  <br/> |<span data-ttu-id="ef2a4-116">这指示是否应将解压缩的 RTF 写入[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的_lpCompressedRTFStream_指针指向的流。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-116">This indicates whether the decompressed RTF is supposed to be written to the stream that is pointed to by the  _lpCompressedRTFStream_ pointer of the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function.</span></span>  <br/> |
|<span data-ttu-id="ef2a4-117">MAPI_NATIVE_BODY</span><span class="sxs-lookup"><span data-stu-id="ef2a4-117">MAPI_NATIVE_BODY</span></span>  <br/> |<span data-ttu-id="ef2a4-118">这指示在返回流之前, 是否将解压缩的流也转换为本机正文。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-118">This indicates whether the decompressed stream is also converted to the native body before returning the stream.</span></span> <span data-ttu-id="ef2a4-119">此标志不能与**MAPI_MODIFY**标志一起使用。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-119">This flag cannot be combined with the **MAPI_MODIFY** flag.</span></span>  <br/> |
   
 <span data-ttu-id="ef2a4-120">_ulInCodePage_</span><span class="sxs-lookup"><span data-stu-id="ef2a4-120">_ulInCodePage_</span></span>
  
> <span data-ttu-id="ef2a4-121">这是邮件的代码页值。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-121">This is the code page value of the message.</span></span> <span data-ttu-id="ef2a4-122">通常, 此值是从邮件的[PidTagInternetCodepage 规范属性](pidtaginternetcodepage-canonical-property.md)获取的。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-122">Typically, this value is obtained from the [PidTagInternetCodepage Canonical Property](pidtaginternetcodepage-canonical-property.md) on the message.</span></span> <span data-ttu-id="ef2a4-123">仅当在_ulFlags_中传递**MAPI_NATIVE_BODY**标志时, 才使用此值。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-123">This value is only used when the **MAPI_NATIVE_BODY** flag is passed in  _ulFlags_.</span></span> <span data-ttu-id="ef2a4-124">否则, 此值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-124">Otherwise, this value is ignored.</span></span>
    
 <span data-ttu-id="ef2a4-125">_ulOutCodePage_</span><span class="sxs-lookup"><span data-stu-id="ef2a4-125">_ulOutCodePage_</span></span>
  
> <span data-ttu-id="ef2a4-126">这是所需的已返回的解压缩流的代码页值。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-126">This is the code page value of the returned decompressed stream that you want.</span></span> <span data-ttu-id="ef2a4-127">如果将此值设置为非零值, 则[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数会将流转换为指定的代码页。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-127">If this is set to a non-zero value, the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function converts the stream to the specified code page.</span></span> <span data-ttu-id="ef2a4-128">如果将此值设置为零值, MAPI 将决定要使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-128">If this is set to a zero value, MAPI decides which code page to use.</span></span> <span data-ttu-id="ef2a4-129">仅当在_ulFlags_中传递**MAPI_NATIVE_BODY**标志且正文格式不是 RTF 时, 才使用此值。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-129">This value is used only when the **MAPI_NATIVE_BODY** flag is passed in  _ulFlags_, and the body format is not RTF.</span></span> <span data-ttu-id="ef2a4-130">否则, 此值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ef2a4-130">Otherwise, this value is ignored.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ef2a4-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef2a4-131">See also</span></span>



[<span data-ttu-id="ef2a4-132">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="ef2a4-132">WrapCompressedRTFStreamEx</span></span>](wrapcompressedrtfstreamex.md)

