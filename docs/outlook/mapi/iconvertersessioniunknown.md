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
ms.openlocfilehash: a89b1a93b2b03f97426a3988739e9b0d8411f113
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775295"
---
# <a name="iconvertersession--iunknown"></a><span data-ttu-id="d0131-103">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d0131-103">IConverterSession : IUnknown</span></span>

  
  
<span data-ttu-id="d0131-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d0131-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d0131-105">允许 MIME 对象和 MAPI 邮件之间的转换。</span><span class="sxs-lookup"><span data-stu-id="d0131-105">Allows conversions between MIME objects and MAPI messages.</span></span> <span data-ttu-id="d0131-106">这可以是中可在 internet 传输邮件。</span><span class="sxs-lookup"><span data-stu-id="d0131-106">This can be useful in transporting messages across the Internet.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d0131-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="d0131-107">Provided by:</span></span>  <br/> |<span data-ttu-id="d0131-108">CLSID_IConverterSession</span><span class="sxs-lookup"><span data-stu-id="d0131-108">CLSID_IConverterSession</span></span>  <br/> |
|<span data-ttu-id="d0131-109">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="d0131-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="d0131-110">IID_IConverterSession</span><span class="sxs-lookup"><span data-stu-id="d0131-110">IID_IConverterSession</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="d0131-111">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="d0131-111">Vtable order</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d0131-112">**[SetAdrBook](iconvertersession-setadrbook.md)**</span><span class="sxs-lookup"><span data-stu-id="d0131-112">**[SetAdrBook](iconvertersession-setadrbook.md)**</span></span> <br/> |<span data-ttu-id="d0131-113">指定到 MIME 转换器 MAPI 解析不明确的地址，将 MAPI 邮件转换为 MIME 流时使用可选 MAPI 通讯簿。</span><span class="sxs-lookup"><span data-stu-id="d0131-113">Specifies an optional MAPI Address Book that the MAPI to MIME converter uses to resolve ambiguous addresses when converting a MAPI message to a MIME stream.</span></span>  <br/> |
|<span data-ttu-id="d0131-114">**[SetEncoding](iconvertersession-setencoding.md)**</span><span class="sxs-lookup"><span data-stu-id="d0131-114">**[SetEncoding](iconvertersession-setencoding.md)**</span></span> <br/> |<span data-ttu-id="d0131-115">初始化转换期间使用的编码。</span><span class="sxs-lookup"><span data-stu-id="d0131-115">Initializes the encoding to use during conversion.</span></span>  <br/> |
| <span data-ttu-id="d0131-116">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d0131-116">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d0131-117">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d0131-117">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="d0131-118">**[MIMEToMAPI](iconvertersession-mimetomapi.md)**</span><span class="sxs-lookup"><span data-stu-id="d0131-118">**[MIMEToMAPI](iconvertersession-mimetomapi.md)**</span></span> <br/> |<span data-ttu-id="d0131-119">将 MIME 流转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="d0131-119">Converts a MIME stream to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="d0131-120">**[MAPIToMIMEStm](iconvertersession-mapitomimestm.md)**</span><span class="sxs-lookup"><span data-stu-id="d0131-120">**[MAPIToMIMEStm](iconvertersession-mapitomimestm.md)**</span></span> <br/> |<span data-ttu-id="d0131-121">将 MAPI 邮件转换为 MIME 流。</span><span class="sxs-lookup"><span data-stu-id="d0131-121">Converts a MAPI message to a MIME stream.</span></span>  <br/> |
| <span data-ttu-id="d0131-122">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d0131-122">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d0131-123">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d0131-123">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="d0131-124">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d0131-124">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d0131-125">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d0131-125">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="d0131-126">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d0131-126">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d0131-127">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d0131-127">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="d0131-128">**[SetTextWrapping](iconvertersession-settextwrapping.md)**</span><span class="sxs-lookup"><span data-stu-id="d0131-128">**[SetTextWrapping](iconvertersession-settextwrapping.md)**</span></span> <br/> |<span data-ttu-id="d0131-129">设置的文字环绕转换器返回中**MAPIToMIMEStm**MIME 流宽度。</span><span class="sxs-lookup"><span data-stu-id="d0131-129">Sets the text wrapping width for a MIME stream that the converter returns in **MAPIToMIMEStm**.</span></span>  <br/> |
|<span data-ttu-id="d0131-130">**[SetSaveFormat](iconvertersession-setsaveformat.md)**</span><span class="sxs-lookup"><span data-stu-id="d0131-130">**[SetSaveFormat](iconvertersession-setsaveformat.md)**</span></span> <br/> |<span data-ttu-id="d0131-131">转换器的返回中**MAPIToMIMEStm**MIME 流的格式设置。</span><span class="sxs-lookup"><span data-stu-id="d0131-131">Sets the format that the converter returns a MIME stream in **MAPIToMIMEStm**.</span></span>  <br/> |
| <span data-ttu-id="d0131-132">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="d0131-132">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="d0131-133">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="d0131-133">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="d0131-134">**[SetCharSet](iconvertersession-setcharset.md)**</span><span class="sxs-lookup"><span data-stu-id="d0131-134">**[SetCharSet](iconvertersession-setcharset.md)**</span></span> <br/> |<span data-ttu-id="d0131-135">指定一个可选的字符设置为 MIME 转换器 MAPI 使用将 MAPI 邮件转换为 MIME 流时。</span><span class="sxs-lookup"><span data-stu-id="d0131-135">Specifies an optional character set that the MAPI to MIME converter uses when converting a MAPI message to a MIME stream.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d0131-136">说明</span><span class="sxs-lookup"><span data-stu-id="d0131-136">Remarks</span></span>

<span data-ttu-id="d0131-137">使用**MAPIToMIMEStm**执行转换之前调用**SetEncoding** 。</span><span class="sxs-lookup"><span data-stu-id="d0131-137">Call **SetEncoding** before using **MAPIToMIMEStm** to perform conversion.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d0131-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0131-138">See also</span></span>



[<span data-ttu-id="d0131-139">关于 MAPI-MIME 转换 API</span><span class="sxs-lookup"><span data-stu-id="d0131-139">About the MAPI-MIME Conversion API</span></span>](about-the-mapi-mime-conversion-api.md)
  
[<span data-ttu-id="d0131-140">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="d0131-140">MAPI Constants</span></span>](mapi-constants.md)

