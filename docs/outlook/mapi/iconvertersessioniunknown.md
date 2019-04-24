---
title: IConverterSession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession
api_type:
- COM
ms.assetid: 24f7a14a-aa6f-4045-054b-4a7aefef25e4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2db55d6318cf02dd131d07b34841922e61605147
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336685"
---
# <a name="iconvertersession--iunknown"></a><span data-ttu-id="d5df2-103">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d5df2-103">IConverterSession : IUnknown</span></span>

  
  
<span data-ttu-id="d5df2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d5df2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d5df2-105">允许在 MIME 对象和 MAPI 邮件之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="d5df2-105">Allows conversions between MIME objects and MAPI messages.</span></span> <span data-ttu-id="d5df2-106">这在通过 Internet 传输邮件时可能很有用。</span><span class="sxs-lookup"><span data-stu-id="d5df2-106">This can be useful in transporting messages across the Internet.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d5df2-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="d5df2-107">Provided by:</span></span>  <br/> |<span data-ttu-id="d5df2-108">CLSID_IConverterSession</span><span class="sxs-lookup"><span data-stu-id="d5df2-108">CLSID_IConverterSession</span></span>  <br/> |
|<span data-ttu-id="d5df2-109">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="d5df2-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="d5df2-110">IID_IConverterSession</span><span class="sxs-lookup"><span data-stu-id="d5df2-110">IID_IConverterSession</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="d5df2-111">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="d5df2-111">Vtable order</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d5df2-112">**[SetAdrBook](iconvertersession-setadrbook.md)**</span><span class="sxs-lookup"><span data-stu-id="d5df2-112">**[SetAdrBook](iconvertersession-setadrbook.md)**</span></span> <br/> |<span data-ttu-id="d5df2-113">指定 mapi 到 mime 转换器在将 MAPI 邮件转换为 MIME 流时用于解析不明确地址的可选 MAPI 通讯簿。</span><span class="sxs-lookup"><span data-stu-id="d5df2-113">Specifies an optional MAPI Address Book that the MAPI to MIME converter uses to resolve ambiguous addresses when converting a MAPI message to a MIME stream.</span></span>  <br/> |
|<span data-ttu-id="d5df2-114">**[SetEncoding](iconvertersession-setencoding.md)**</span><span class="sxs-lookup"><span data-stu-id="d5df2-114">**[SetEncoding](iconvertersession-setencoding.md)**</span></span> <br/> |<span data-ttu-id="d5df2-115">初始化要在转换过程中使用的编码。</span><span class="sxs-lookup"><span data-stu-id="d5df2-115">Initializes the encoding to use during conversion.</span></span>  <br/> |
| <span data-ttu-id="d5df2-116">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d5df2-116">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d5df2-117">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d5df2-117">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="d5df2-118">**[MIMEToMAPI](iconvertersession-mimetomapi.md)**</span><span class="sxs-lookup"><span data-stu-id="d5df2-118">**[MIMEToMAPI](iconvertersession-mimetomapi.md)**</span></span> <br/> |<span data-ttu-id="d5df2-119">将 MIME 流转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="d5df2-119">Converts a MIME stream to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="d5df2-120">**[MAPIToMIMEStm](iconvertersession-mapitomimestm.md)**</span><span class="sxs-lookup"><span data-stu-id="d5df2-120">**[MAPIToMIMEStm](iconvertersession-mapitomimestm.md)**</span></span> <br/> |<span data-ttu-id="d5df2-121">将 MAPI 邮件转换为 MIME 流。</span><span class="sxs-lookup"><span data-stu-id="d5df2-121">Converts a MAPI message to a MIME stream.</span></span>  <br/> |
| <span data-ttu-id="d5df2-122">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d5df2-122">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d5df2-123">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d5df2-123">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="d5df2-124">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d5df2-124">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d5df2-125">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d5df2-125">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="d5df2-126">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d5df2-126">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d5df2-127">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d5df2-127">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="d5df2-128">**[SetTextWrapping](iconvertersession-settextwrapping.md)**</span><span class="sxs-lookup"><span data-stu-id="d5df2-128">**[SetTextWrapping](iconvertersession-settextwrapping.md)**</span></span> <br/> |<span data-ttu-id="d5df2-129">设置转换器在**MAPIToMIMEStm**中返回的 MIME 流的文本换行宽度。</span><span class="sxs-lookup"><span data-stu-id="d5df2-129">Sets the text wrapping width for a MIME stream that the converter returns in **MAPIToMIMEStm**.</span></span>  <br/> |
|<span data-ttu-id="d5df2-130">**[SetSaveFormat](iconvertersession-setsaveformat.md)**</span><span class="sxs-lookup"><span data-stu-id="d5df2-130">**[SetSaveFormat](iconvertersession-setsaveformat.md)**</span></span> <br/> |<span data-ttu-id="d5df2-131">设置转换器在**MAPIToMIMEStm**中返回 MIME 流的格式。</span><span class="sxs-lookup"><span data-stu-id="d5df2-131">Sets the format that the converter returns a MIME stream in **MAPIToMIMEStm**.</span></span>  <br/> |
| <span data-ttu-id="d5df2-132">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d5df2-132">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d5df2-133">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d5df2-133">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="d5df2-134">**[SetCharSet](iconvertersession-setcharset.md)**</span><span class="sxs-lookup"><span data-stu-id="d5df2-134">**[SetCharSet](iconvertersession-setcharset.md)**</span></span> <br/> |<span data-ttu-id="d5df2-135">指定 mapi 到 mime 转换器在将 mapi 邮件转换为 mime 流时使用的可选字符集。</span><span class="sxs-lookup"><span data-stu-id="d5df2-135">Specifies an optional character set that the MAPI to MIME converter uses when converting a MAPI message to a MIME stream.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d5df2-136">注解</span><span class="sxs-lookup"><span data-stu-id="d5df2-136">Remarks</span></span>

<span data-ttu-id="d5df2-137">在使用**MAPIToMIMEStm**执行转换之前调用**SetEncoding** 。</span><span class="sxs-lookup"><span data-stu-id="d5df2-137">Call **SetEncoding** before using **MAPIToMIMEStm** to perform conversion.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d5df2-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5df2-138">See also</span></span>



[<span data-ttu-id="d5df2-139">关于 MAPI-MIME 转换 API</span><span class="sxs-lookup"><span data-stu-id="d5df2-139">About the MAPI-MIME Conversion API</span></span>](about-the-mapi-mime-conversion-api.md)
  
[<span data-ttu-id="d5df2-140">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="d5df2-140">MAPI Constants</span></span>](mapi-constants.md)

