---
title: 打开附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0350698-5304-40cd-903d-279471f3c226
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 39da1e02622d81cd12a2d4673b827d49bf418128
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430621"
---
# <a name="opening-an-attachment"></a><span data-ttu-id="1abed-103">打开附件</span><span class="sxs-lookup"><span data-stu-id="1abed-103">Opening an attachment</span></span>

<span data-ttu-id="1abed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1abed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1abed-105">打开附件涉及显示其数据。</span><span class="sxs-lookup"><span data-stu-id="1abed-105">Opening an attachment involves displaying its data.</span></span> <span data-ttu-id="1abed-106">例如，打开文件附件时，将显示文件的内容。</span><span class="sxs-lookup"><span data-stu-id="1abed-106">For example, when a file attachment is opened, the contents of the file are displayed.</span></span> <span data-ttu-id="1abed-107">虽然邮件和文件夹是使用其条目标识符打开的，但附件是使用附件编号打开的 **，PR_ATTACH_NUM** 属性。</span><span class="sxs-lookup"><span data-stu-id="1abed-107">Whereas messages and folders are opened using their entry identifiers, attachments are opened using their attachment numbers — **PR_ATTACH_NUM** properties.</span></span> <span data-ttu-id="1abed-108">有关详细信息，请参阅 **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="1abed-108">For more information, see **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)).</span></span> <span data-ttu-id="1abed-109">附件编号通过邮件的附件表提供。</span><span class="sxs-lookup"><span data-stu-id="1abed-109">Attachment numbers are available through a message's attachment table.</span></span>
  
### <a name="to-open-all-attachments-in-a-message"></a><span data-ttu-id="1abed-110">打开邮件中所有附件</span><span class="sxs-lookup"><span data-stu-id="1abed-110">To open all attachments in a message</span></span>
  
1. <span data-ttu-id="1abed-111">调用邮件的 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md) 方法以访问其附件表。</span><span class="sxs-lookup"><span data-stu-id="1abed-111">Call the message's [IMessage::GetAttachmentTable](imessage-getattachmenttable.md) method to access its attachment table.</span></span> 
    
2. <span data-ttu-id="1abed-112">调用 [HrQueryAllRows](hrqueryallrows.md) 以检索表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="1abed-112">Call [HrQueryAllRows](hrqueryallrows.md) to retrieve all the rows in the table.</span></span> 
    
3. <span data-ttu-id="1abed-113">对于每一行：</span><span class="sxs-lookup"><span data-stu-id="1abed-113">For each row:</span></span> 
    
    1. <span data-ttu-id="1abed-114">通过向邮件的 **IMessage：：OpenAttach** 方法的调用中传递 **PR_ATTACH_NUM** 列中表示的附件编号，打开附件。</span><span class="sxs-lookup"><span data-stu-id="1abed-114">Open the attachment by passing the attachment number represented in the **PR_ATTACH_NUM** column in a call to the message's **IMessage::OpenAttach** method.</span></span> <span data-ttu-id="1abed-115">有关详细信息，请参阅 [IMessage：：OpenAttach](imessage-openattach.md)。</span><span class="sxs-lookup"><span data-stu-id="1abed-115">For more information, see [IMessage::OpenAttach](imessage-openattach.md).</span></span> <span data-ttu-id="1abed-116">**OpenAttach** 返回一个指向 **IAttach** 实现（提供对附件属性的访问）的指针。</span><span class="sxs-lookup"><span data-stu-id="1abed-116">**OpenAttach** returns a pointer to an **IAttach** implementation that provides access to attachment properties.</span></span> 
        
    2. <span data-ttu-id="1abed-117">调用附件的 **IMAPIProp：：GetProps** 方法来 **检索其PR_ATTACH_METHOD** 属性。</span><span class="sxs-lookup"><span data-stu-id="1abed-117">Call the attachment's **IMAPIProp::GetProps** method to retrieve its **PR_ATTACH_METHOD** property.</span></span> <span data-ttu-id="1abed-118">有关详细信息，请参阅 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="1abed-118">For more information, see [IMAPIProp::GetProps](imapiprop-getprops.md) and **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)).</span></span>
        
    3. <span data-ttu-id="1abed-119">如果 **PR_ATTACH_METHOD** 设置为 ATTACH_BY_REF_ONLY，请调用 **IMAPIProp：：GetProps** 以检索 **PR_ATTACH_PATHNAME** 属性。</span><span class="sxs-lookup"><span data-stu-id="1abed-119">If **PR_ATTACH_METHOD** is set to ATTACH_BY_REF_ONLY, call **IMAPIProp::GetProps** to retrieve the **PR_ATTACH_PATHNAME** property.</span></span> <span data-ttu-id="1abed-120">有关详细信息，请参阅 **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="1abed-120">For more information, see **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)).</span></span>
        
    4. <span data-ttu-id="1abed-121">如果 **PR \_ ATTACH_METHOD** 设置为 ATTACH \_ BY_VALUE，请调用 **IMAPIProp：：OpenProperty** 以使用 **IStream** 接口打开 **PR \_ ATTACH_DATA_BIN** 属性。</span><span class="sxs-lookup"><span data-stu-id="1abed-121">If **PR\_ATTACH_METHOD** is set to ATTACH\_BY_VALUE, call **IMAPIProp::OpenProperty** to open the **PR\_ATTACH_DATA_BIN** property with the **IStream** interface.</span></span> <span data-ttu-id="1abed-122">请参阅此过程后的示例代码。</span><span class="sxs-lookup"><span data-stu-id="1abed-122">See the sample code following this procedure.</span></span> <span data-ttu-id="1abed-123">有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 和 **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="1abed-123">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)).</span></span>
        
    5. <span data-ttu-id="1abed-124">如果 **PR_ATTACH_METHOD** 设置为 OLE 2 ATTACH_OLE附件是 OLE 2 对象：</span><span class="sxs-lookup"><span data-stu-id="1abed-124">If **PR_ATTACH_METHOD** is set to ATTACH_OLE and the attachment is an OLE 2 object:</span></span> 
        
        1. <span data-ttu-id="1abed-125">调用 **IMAPIProp：：OpenProperty** 以使用 **IStreamDocfile** **\_ ATTACH_DATA_OBJ** PR 属性打开 PR 属性。</span><span class="sxs-lookup"><span data-stu-id="1abed-125">Call **IMAPIProp::OpenProperty** to open the **PR\_ATTACH_DATA_OBJ** property with the **IStreamDocfile** interface.</span></span> <span data-ttu-id="1abed-126">尝试使用此接口，因为它是保证使用开销最少的结构化存储的 **IStream** 实现。</span><span class="sxs-lookup"><span data-stu-id="1abed-126">Attempt to use this interface because it is an implementation of **IStream** guaranteed to work with structured storage with the least amount of overhead.</span></span> <span data-ttu-id="1abed-127">有关详细信息，请参阅 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="1abed-127">For more information, see **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)).</span></span>
            
        2. <span data-ttu-id="1abed-128">如果 **OpenProperty** 调用失败，请再次调用它，以检索 **PR_ATTACH_DATA_BIN** **IStreamDocfile** 接口的 PR_ATTACH_DATA_BIN 属性。</span><span class="sxs-lookup"><span data-stu-id="1abed-128">If the **OpenProperty** call fails, call it again to retrieve the **PR_ATTACH_DATA_BIN** property with the **IStreamDocfile** interface.</span></span> 
            
        3. <span data-ttu-id="1abed-129">如果第二 **个 OpenProperty** 调用失败，请再次尝试调用 **OpenProperty\*\*\*\*以检索** PR_ATTACH_DATA_OBJ。</span><span class="sxs-lookup"><span data-stu-id="1abed-129">If this second **OpenProperty** call fails, try again to call **OpenProperty** to retrieve **PR_ATTACH_DATA_OBJ**.</span></span> <span data-ttu-id="1abed-130">但是，不是指定 **IStreamDocfile**，而是指定 **IStorage** 接口。</span><span class="sxs-lookup"><span data-stu-id="1abed-130">However, rather than specifying **IStreamDocfile**, specify the **IStorage** interface.</span></span> 
    
4. <span data-ttu-id="1abed-131">如果 **PR_ATTACH_METHOD** 设置为 ATTACH_EMBEDDED_MSG，则值 **PR_ATTACH_DATA_OBJ包含错误** 并不少见。</span><span class="sxs-lookup"><span data-stu-id="1abed-131">If **PR_ATTACH_METHOD** is set to ATTACH_EMBEDDED_MSG, it is not unusual for the value of **PR_ATTACH_DATA_OBJ** to contain an error.</span></span> <span data-ttu-id="1abed-132">这是因为你和表实施者无法就要返回的对象类型达成一致。</span><span class="sxs-lookup"><span data-stu-id="1abed-132">This is because you and the table implementer have no way to agree on the type of object to return.</span></span> <span data-ttu-id="1abed-133">若要检索指向附加邮件的指针，请用 **IMessage：：OpenAttach 打开附件**。</span><span class="sxs-lookup"><span data-stu-id="1abed-133">To retrieve a pointer to the attached message, open the attachment using **IMessage::OpenAttach**.</span></span> <span data-ttu-id="1abed-134">然后通过调用其 **IMAPIProp：：OpenProperty 方法访问附件** 数据。</span><span class="sxs-lookup"><span data-stu-id="1abed-134">Then access the attachment data by calling its **IMAPIProp::OpenProperty** method.</span></span> <span data-ttu-id="1abed-135">有关详细信息，请参阅 [IMessage：：OpenAttach](imessage-openattach.md) 和 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="1abed-135">For more information, see [IMessage::OpenAttach](imessage-openattach.md) and [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
    
<span data-ttu-id="1abed-136">您可以请求以读/写或只读模式打开附件。</span><span class="sxs-lookup"><span data-stu-id="1abed-136">You can request that an attachment is opened in read/write or read-only mode.</span></span> <span data-ttu-id="1abed-137">只读是默认模式，许多邮件存储提供程序在此模式下打开所有附件，而不考虑客户端请求什么。</span><span class="sxs-lookup"><span data-stu-id="1abed-137">Read-only is the default mode, and many message store providers open all attachments in this mode regardless of what clients request.</span></span> <span data-ttu-id="1abed-138">传递 MAPI_BEST_ACCESS 标志以请求邮件存储提供程序授予其可以授予的最高访问权限级别，然后检索打开的附件 **的 PR_ACCESS_LEVEL** 属性以确定实际授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="1abed-138">Pass the MAPI_BEST_ACCESS flag to request that the message store provider grant the highest level of access it can and then retrieve the open attachment's **PR_ACCESS_LEVEL** property to determine the level of access that was actually granted.</span></span> <span data-ttu-id="1abed-139">有关详细信息，请参阅 **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="1abed-139">For more information, see **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)).</span></span>
  
<span data-ttu-id="1abed-140">以下示例演示如何在附件的 PR 属性中打开ATTACH_DATA_BIN数据。 **\_**</span><span class="sxs-lookup"><span data-stu-id="1abed-140">The following example shows how to open the data in an attachment's **PR\_ATTACH_DATA_BIN** property.</span></span> <span data-ttu-id="1abed-141">它将指针分配给两个流：一个针对文件，一个针对附件。</span><span class="sxs-lookup"><span data-stu-id="1abed-141">It allocates pointers to two streams: one for the file and one for the attachment.</span></span> <span data-ttu-id="1abed-142">**OpenStreamOnFile** 函数以只读模式打开文件流。</span><span class="sxs-lookup"><span data-stu-id="1abed-142">The **OpenStreamOnFile** function opens the file stream in read-only mode.</span></span> <span data-ttu-id="1abed-143">对附件 **的 IMAPIProp：：OpenProperty** 方法的调用将在读/写模式下打开附件流。</span><span class="sxs-lookup"><span data-stu-id="1abed-143">The call to the attachment's **IMAPIProp::OpenProperty** method opens the attachment stream in read/write mode.</span></span> <span data-ttu-id="1abed-144">有关详细信息，请参阅 **PR_ATTACH_DATA_BIN** [、OpenStreamOnFile](openstreamonfile.md)和 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="1abed-144">For more information, see **PR_ATTACH_DATA_BIN**, [OpenStreamOnFile](openstreamonfile.md), and [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="1abed-145">然后，代码将文件流复制到附件流并释放这两个流。</span><span class="sxs-lookup"><span data-stu-id="1abed-145">The code then copies from the file stream to the attachment stream and releases both streams.</span></span>
  
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


