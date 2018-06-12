---
title: 打开附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0350698-5304-40cd-903d-279471f3c226
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3875e51868e882ca454c06949347327a21a93eb9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776547"
---
# <a name="opening-an-attachment"></a><span data-ttu-id="fb642-103">打开附件</span><span class="sxs-lookup"><span data-stu-id="fb642-103">Opening an attachment</span></span>

<span data-ttu-id="fb642-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fb642-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fb642-105">打开附件涉及显示其数据。</span><span class="sxs-lookup"><span data-stu-id="fb642-105">Opening an attachment involves displaying its data.</span></span> <span data-ttu-id="fb642-106">例如，当打开的文件附件时，将显示文件的内容。</span><span class="sxs-lookup"><span data-stu-id="fb642-106">For example, when a file attachment is opened, the contents of the file are displayed.</span></span> <span data-ttu-id="fb642-107">使用其条目标识符打开邮件和文件夹，而使用其附件号码打开附件 — **PR_ATTACH_NUM**属性。</span><span class="sxs-lookup"><span data-stu-id="fb642-107">Whereas messages and folders are opened using their entry identifiers, attachments are opened using their attachment numbers — **PR_ATTACH_NUM** properties.</span></span> <span data-ttu-id="fb642-108">有关详细信息，请参阅**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="fb642-108">For more information, see **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)).</span></span> <span data-ttu-id="fb642-109">可通过邮件的附件表都附件号码。</span><span class="sxs-lookup"><span data-stu-id="fb642-109">Attachment numbers are available through a message's attachment table.</span></span>
  
### <a name="to-open-all-attachments-in-a-message"></a><span data-ttu-id="fb642-110">若要打开邮件中的所有附件</span><span class="sxs-lookup"><span data-stu-id="fb642-110">To open all attachments in a message</span></span>
  
1. <span data-ttu-id="fb642-111">调用消息的[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)方法，以访问其附件表。</span><span class="sxs-lookup"><span data-stu-id="fb642-111">Call the message's [IMessage::GetAttachmentTable](imessage-getattachmenttable.md) method to access its attachment table.</span></span> 
    
2. <span data-ttu-id="fb642-112">调用[HrQueryAllRows](hrqueryallrows.md)检索表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="fb642-112">Call [HrQueryAllRows](hrqueryallrows.md) to retrieve all the rows in the table.</span></span> 
    
3. <span data-ttu-id="fb642-113">对于每个行：</span><span class="sxs-lookup"><span data-stu-id="fb642-113">For each row:</span></span> 
    
    1. <span data-ttu-id="fb642-114">通过将传递表示对消息的**IMessage::OpenAttach**方法的调用的**PR_ATTACH_NUM**列中的附件号码打开附件。</span><span class="sxs-lookup"><span data-stu-id="fb642-114">Open the attachment by passing the attachment number represented in the **PR_ATTACH_NUM** column in a call to the message's **IMessage::OpenAttach** method.</span></span> <span data-ttu-id="fb642-115">有关详细信息，请参阅[IMessage::OpenAttach](imessage-openattach.md)。</span><span class="sxs-lookup"><span data-stu-id="fb642-115">For more information, see [IMessage::OpenAttach](imessage-openattach.md).</span></span> <span data-ttu-id="fb642-116">**OpenAttach**提供对附件属性访问**IAttach**实现返回的指针。</span><span class="sxs-lookup"><span data-stu-id="fb642-116">**OpenAttach** returns a pointer to an **IAttach** implementation that provides access to attachment properties.</span></span> 
        
    2. <span data-ttu-id="fb642-117">调用附件的**IMAPIProp::GetProps**方法来检索其**PR_ATTACH_METHOD**属性。</span><span class="sxs-lookup"><span data-stu-id="fb642-117">Call the attachment's **IMAPIProp::GetProps** method to retrieve its **PR_ATTACH_METHOD** property.</span></span> <span data-ttu-id="fb642-118">有关详细信息，请参阅[IMAPIProp::GetProps](imapiprop-getprops.md)和**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="fb642-118">For more information, see [IMAPIProp::GetProps](imapiprop-getprops.md) and **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)).</span></span>
        
    3. <span data-ttu-id="fb642-119">如果**PR_ATTACH_METHOD**设置为 ATTACH_BY_REF_ONLY，调用**IMAPIProp::GetProps**检索**PR_ATTACH_PATHNAME**属性。</span><span class="sxs-lookup"><span data-stu-id="fb642-119">If **PR_ATTACH_METHOD** is set to ATTACH_BY_REF_ONLY, call **IMAPIProp::GetProps** to retrieve the **PR_ATTACH_PATHNAME** property.</span></span> <span data-ttu-id="fb642-120">有关详细信息，请参阅**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="fb642-120">For more information, see **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)).</span></span>
        
    4. <span data-ttu-id="fb642-121">如果**PR\_ATTACH_METHOD**设置为附加\_BY_VALUE，呼叫**IMAPIProp::OpenProperty**打开**PR\_ATTACH_DATA_BIN**属性与**IStream**接口。</span><span class="sxs-lookup"><span data-stu-id="fb642-121">If **PR\_ATTACH_METHOD** is set to ATTACH\_BY_VALUE, call **IMAPIProp::OpenProperty** to open the **PR\_ATTACH_DATA_BIN** property with the **IStream** interface.</span></span> <span data-ttu-id="fb642-122">请参阅此过程的示例代码。</span><span class="sxs-lookup"><span data-stu-id="fb642-122">See the sample code following this procedure.</span></span> <span data-ttu-id="fb642-123">有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)和**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="fb642-123">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)).</span></span>
        
    5. <span data-ttu-id="fb642-124">如果**PR_ATTACH_METHOD**设置为 ATTACH_OLE 和附件是 OLE 2 对象：</span><span class="sxs-lookup"><span data-stu-id="fb642-124">If **PR_ATTACH_METHOD** is set to ATTACH_OLE and the attachment is an OLE 2 object:</span></span> 
        
        1. <span data-ttu-id="fb642-125">调用**IMAPIProp::OpenProperty**打开**PR\_ATTACH_DATA_OBJ**属性与**IStreamDocfile**接口。</span><span class="sxs-lookup"><span data-stu-id="fb642-125">Call **IMAPIProp::OpenProperty** to open the **PR\_ATTACH_DATA_OBJ** property with the **IStreamDocfile** interface.</span></span> <span data-ttu-id="fb642-126">试图使用此接口，因为它是**IStream**保证使用结构化存储文件以开销最少的实现。</span><span class="sxs-lookup"><span data-stu-id="fb642-126">Attempt to use this interface because it is an implementation of **IStream** guaranteed to work with structured storage with the least amount of overhead.</span></span> <span data-ttu-id="fb642-127">有关详细信息，请参阅**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="fb642-127">For more information, see **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)).</span></span>
            
        2. <span data-ttu-id="fb642-128">如果**OpenProperty**调用失败，可调用它再次以检索**IStreamDocfile**接口的**PR_ATTACH_DATA_BIN**属性。</span><span class="sxs-lookup"><span data-stu-id="fb642-128">If the **OpenProperty** call fails, call it again to retrieve the **PR_ATTACH_DATA_BIN** property with the **IStreamDocfile** interface.</span></span> 
            
        3. <span data-ttu-id="fb642-129">如果此第二个**OpenProperty**调用失败，则重试呼叫**OpenProperty**检索**PR_ATTACH_DATA_OBJ**。</span><span class="sxs-lookup"><span data-stu-id="fb642-129">If this second **OpenProperty** call fails, try again to call **OpenProperty** to retrieve **PR_ATTACH_DATA_OBJ**.</span></span> <span data-ttu-id="fb642-130">但是，而不是指定**IStreamDocfile**，指定**IStorage**接口。</span><span class="sxs-lookup"><span data-stu-id="fb642-130">However, rather than specifying **IStreamDocfile**, specify the **IStorage** interface.</span></span> 
    
4. <span data-ttu-id="fb642-131">如果**PR_ATTACH_METHOD**设置为 ATTACH_EMBEDDED_MSG，则不特殊**PR_ATTACH_DATA_OBJ**包含错误的值。</span><span class="sxs-lookup"><span data-stu-id="fb642-131">If **PR_ATTACH_METHOD** is set to ATTACH_EMBEDDED_MSG, it is not unusual for the value of **PR_ATTACH_DATA_OBJ** to contain an error.</span></span> <span data-ttu-id="fb642-132">这是对象的因为您并表实施没有任何办法达成一致要返回类型。</span><span class="sxs-lookup"><span data-stu-id="fb642-132">This is because you and the table implementer have no way to agree on the type of object to return.</span></span> <span data-ttu-id="fb642-133">若要检索指向附加的邮件的指针，打开使用**IMessage::OpenAttach**附件。</span><span class="sxs-lookup"><span data-stu-id="fb642-133">To retrieve a pointer to the attached message, open the attachment using **IMessage::OpenAttach**.</span></span> <span data-ttu-id="fb642-134">然后通过调用其**IMAPIProp::OpenProperty**方法访问附件数据。</span><span class="sxs-lookup"><span data-stu-id="fb642-134">Then access the attachment data by calling its **IMAPIProp::OpenProperty** method.</span></span> <span data-ttu-id="fb642-135">有关详细信息，请参阅[IMessage::OpenAttach](imessage-openattach.md)和[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="fb642-135">For more information, see [IMessage::OpenAttach](imessage-openattach.md) and [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
    
<span data-ttu-id="fb642-136">您可以请求的读/写或只读模式中打开的附件。</span><span class="sxs-lookup"><span data-stu-id="fb642-136">You can request that an attachment is opened in read/write or read-only mode.</span></span> <span data-ttu-id="fb642-137">只读是默认的模式，并许多消息存储提供程序无论客户端的请求此模式中打开所有附件。</span><span class="sxs-lookup"><span data-stu-id="fb642-137">Read-only is the default mode, and many message store providers open all attachments in this mode regardless of what clients request.</span></span> <span data-ttu-id="fb642-138">传入请求的消息存储提供程序授予的访问它可以，然后检索打开的附件的**PR_ACCESS_LEVEL**属性可以确定的实际授予的访问级别最高级别 MAPI_BEST_ACCESS 标志。</span><span class="sxs-lookup"><span data-stu-id="fb642-138">Pass the MAPI_BEST_ACCESS flag to request that the message store provider grant the highest level of access it can and then retrieve the open attachment's **PR_ACCESS_LEVEL** property to determine the level of access that was actually granted.</span></span> <span data-ttu-id="fb642-139">有关详细信息，请参阅**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="fb642-139">For more information, see **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)).</span></span>
  
<span data-ttu-id="fb642-140">下面的示例演示如何打开的附件中的数据**PR\_ATTACH_DATA_BIN**属性。</span><span class="sxs-lookup"><span data-stu-id="fb642-140">The following example shows how to open the data in an attachment's **PR\_ATTACH_DATA_BIN** property.</span></span> <span data-ttu-id="fb642-141">分配了指向两个流： 一个用于文件，一个附件。</span><span class="sxs-lookup"><span data-stu-id="fb642-141">It allocates pointers to two streams: one for the file and one for the attachment.</span></span> <span data-ttu-id="fb642-142">**OpenStreamOnFile**函数以只读模式打开文件流。</span><span class="sxs-lookup"><span data-stu-id="fb642-142">The **OpenStreamOnFile** function opens the file stream in read-only mode.</span></span> <span data-ttu-id="fb642-143">对附件的**IMAPIProp::OpenProperty**方法的调用以读/写模式打开附件流。</span><span class="sxs-lookup"><span data-stu-id="fb642-143">The call to the attachment's **IMAPIProp::OpenProperty** method opens the attachment stream in read/write mode.</span></span> <span data-ttu-id="fb642-144">有关详细信息，请参阅**PR_ATTACH_DATA_BIN**、 [OpenStreamOnFile](openstreamonfile.md)和[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="fb642-144">For more information, see **PR_ATTACH_DATA_BIN**, [OpenStreamOnFile](openstreamonfile.md), and [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="fb642-145">该代码，然后将文件流复制到附件流并释放两个流。</span><span class="sxs-lookup"><span data-stu-id="fb642-145">The code then copies from the file stream to the attachment stream and releases both streams.</span></span>
  
```cpp
LPSTREAM pStreamFile, pStreamAtt;
HRESULT hr;
hr = OpenStreamOnFile (MAPIAllocateBuffer, MAPIFreeBuffer,
                       STGM_READ, "myfile.doc", NULL, &pStreamFile);
if (HR_SUCCEEDED(hr))
{
    // Open the destination stream in the attachment object
    hr = pAttach->OpenProperty (PR_ATTACH_DATA_BIN,
                                &IID_IStream,
                                0,
                                MAPI_MODIFY | MAPI_CREATE,
                                (LPUNKNOWN *)&pStreamAtt);
    if (HR_SUCCEEDED(hr))
    {
        STATSTG StatInfo;
        pStreamFile->Stat (&StatInfo, STATFLAG_NONAME);
        hResult = pStreamFile->CopyTo (pStreamAtt, StatInfo.cbSize,
                                       NULL, NULL);
        pStreamAtt->Release();
    }
    pStreamFile->Release();
}
```


