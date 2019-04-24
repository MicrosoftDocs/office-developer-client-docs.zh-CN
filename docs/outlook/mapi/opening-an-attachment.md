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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326171"
---
# <a name="opening-an-attachment"></a><span data-ttu-id="6edfb-103">打开附件</span><span class="sxs-lookup"><span data-stu-id="6edfb-103">Opening an attachment</span></span>

<span data-ttu-id="6edfb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6edfb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6edfb-105">打开附件时需要显示其数据。</span><span class="sxs-lookup"><span data-stu-id="6edfb-105">Opening an attachment involves displaying its data.</span></span> <span data-ttu-id="6edfb-106">例如, 打开文件附件时, 将显示文件的内容。</span><span class="sxs-lookup"><span data-stu-id="6edfb-106">For example, when a file attachment is opened, the contents of the file are displayed.</span></span> <span data-ttu-id="6edfb-107">邮件和文件夹使用其条目标识符打开, 附件使用附件号码 ( **PR_ATTACH_NUM**属性) 打开。</span><span class="sxs-lookup"><span data-stu-id="6edfb-107">Whereas messages and folders are opened using their entry identifiers, attachments are opened using their attachment numbers — **PR_ATTACH_NUM** properties.</span></span> <span data-ttu-id="6edfb-108">有关详细信息, 请参阅**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6edfb-108">For more information, see **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)).</span></span> <span data-ttu-id="6edfb-109">可通过邮件的附件表使用附件号码。</span><span class="sxs-lookup"><span data-stu-id="6edfb-109">Attachment numbers are available through a message's attachment table.</span></span>
  
### <a name="to-open-all-attachments-in-a-message"></a><span data-ttu-id="6edfb-110">打开邮件中的所有附件</span><span class="sxs-lookup"><span data-stu-id="6edfb-110">To open all attachments in a message</span></span>
  
1. <span data-ttu-id="6edfb-111">调用邮件的[IMessage:: GetAttachmentTable](imessage-getattachmenttable.md)方法以访问其附件表。</span><span class="sxs-lookup"><span data-stu-id="6edfb-111">Call the message's [IMessage::GetAttachmentTable](imessage-getattachmenttable.md) method to access its attachment table.</span></span> 
    
2. <span data-ttu-id="6edfb-112">调用[HrQueryAllRows](hrqueryallrows.md)以检索表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="6edfb-112">Call [HrQueryAllRows](hrqueryallrows.md) to retrieve all the rows in the table.</span></span> 
    
3. <span data-ttu-id="6edfb-113">对于每一行:</span><span class="sxs-lookup"><span data-stu-id="6edfb-113">For each row:</span></span> 
    
    1. <span data-ttu-id="6edfb-114">通过在对邮件的**IMessage:: OpenAttach**方法的调用中传递 " **PR_ATTACH_NUM** " 列中表示的附件编号来打开附件。</span><span class="sxs-lookup"><span data-stu-id="6edfb-114">Open the attachment by passing the attachment number represented in the **PR_ATTACH_NUM** column in a call to the message's **IMessage::OpenAttach** method.</span></span> <span data-ttu-id="6edfb-115">有关详细信息, 请参阅[IMessage:: OpenAttach](imessage-openattach.md)。</span><span class="sxs-lookup"><span data-stu-id="6edfb-115">For more information, see [IMessage::OpenAttach](imessage-openattach.md).</span></span> <span data-ttu-id="6edfb-116">**OpenAttach**返回指向**IAttach**实现的指针, 该实现提供对附件属性的访问。</span><span class="sxs-lookup"><span data-stu-id="6edfb-116">**OpenAttach** returns a pointer to an **IAttach** implementation that provides access to attachment properties.</span></span> 
        
    2. <span data-ttu-id="6edfb-117">调用附件的**IMAPIProp:: GetProps**方法以检索其**PR_ATTACH_METHOD**属性。</span><span class="sxs-lookup"><span data-stu-id="6edfb-117">Call the attachment's **IMAPIProp::GetProps** method to retrieve its **PR_ATTACH_METHOD** property.</span></span> <span data-ttu-id="6edfb-118">有关详细信息, 请参阅[IMAPIProp:: GetProps](imapiprop-getprops.md) and **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6edfb-118">For more information, see [IMAPIProp::GetProps](imapiprop-getprops.md) and **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)).</span></span>
        
    3. <span data-ttu-id="6edfb-119">如果**PR_ATTACH_METHOD**设置为 ATTACH_BY_REF_ONLY, 则调用**IMAPIProp:: GetProps**以检索**PR_ATTACH_PATHNAME**属性。</span><span class="sxs-lookup"><span data-stu-id="6edfb-119">If **PR_ATTACH_METHOD** is set to ATTACH_BY_REF_ONLY, call **IMAPIProp::GetProps** to retrieve the **PR_ATTACH_PATHNAME** property.</span></span> <span data-ttu-id="6edfb-120">有关详细信息, 请参阅**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6edfb-120">For more information, see **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)).</span></span>
        
    4. <span data-ttu-id="6edfb-121">如果**PR\_ATTACH_METHOD**设置为 ATTACH\_BY_VALUE, 则调用**IMAPIProp:: OpenProperty**以使用**IStream**接口打开 " **PR\_ATTACH_DATA_BIN** " 属性。</span><span class="sxs-lookup"><span data-stu-id="6edfb-121">If **PR\_ATTACH_METHOD** is set to ATTACH\_BY_VALUE, call **IMAPIProp::OpenProperty** to open the **PR\_ATTACH_DATA_BIN** property with the **IStream** interface.</span></span> <span data-ttu-id="6edfb-122">请参阅此过程后面的示例代码。</span><span class="sxs-lookup"><span data-stu-id="6edfb-122">See the sample code following this procedure.</span></span> <span data-ttu-id="6edfb-123">有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md) and **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6edfb-123">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)).</span></span>
        
    5. <span data-ttu-id="6edfb-124">如果**PR_ATTACH_METHOD**设置为 ATTACH_OLE, 并且附件是 OLE 2 对象:</span><span class="sxs-lookup"><span data-stu-id="6edfb-124">If **PR_ATTACH_METHOD** is set to ATTACH_OLE and the attachment is an OLE 2 object:</span></span> 
        
        1. <span data-ttu-id="6edfb-125">调用**IMAPIProp:: OpenProperty**以使用**IStreamDocfile**接口打开 " **PR\_ATTACH_DATA_OBJ** " 属性。</span><span class="sxs-lookup"><span data-stu-id="6edfb-125">Call **IMAPIProp::OpenProperty** to open the **PR\_ATTACH_DATA_OBJ** property with the **IStreamDocfile** interface.</span></span> <span data-ttu-id="6edfb-126">尝试使用此接口, 因为它是确保对具有最少开销的结构化存储进行处理的**IStream**实现。</span><span class="sxs-lookup"><span data-stu-id="6edfb-126">Attempt to use this interface because it is an implementation of **IStream** guaranteed to work with structured storage with the least amount of overhead.</span></span> <span data-ttu-id="6edfb-127">有关详细信息, 请参阅**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6edfb-127">For more information, see **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)).</span></span>
            
        2. <span data-ttu-id="6edfb-128">如果**OpenProperty**调用失败, 请再次调用它, 以使用**IStreamDocfile**接口检索**PR_ATTACH_DATA_BIN**属性。</span><span class="sxs-lookup"><span data-stu-id="6edfb-128">If the **OpenProperty** call fails, call it again to retrieve the **PR_ATTACH_DATA_BIN** property with the **IStreamDocfile** interface.</span></span> 
            
        3. <span data-ttu-id="6edfb-129">如果此第二个**OpenProperty**调用失败, 请再次尝试调用**OpenProperty**以检索**PR_ATTACH_DATA_OBJ**。</span><span class="sxs-lookup"><span data-stu-id="6edfb-129">If this second **OpenProperty** call fails, try again to call **OpenProperty** to retrieve **PR_ATTACH_DATA_OBJ**.</span></span> <span data-ttu-id="6edfb-130">但是, 不是指定**IStreamDocfile**, 而是指定**IStorage**接口。</span><span class="sxs-lookup"><span data-stu-id="6edfb-130">However, rather than specifying **IStreamDocfile**, specify the **IStorage** interface.</span></span> 
    
4. <span data-ttu-id="6edfb-131">如果**PR_ATTACH_METHOD**设置为 ATTACH_EMBEDDED_MSG, 则**PR_ATTACH_DATA_OBJ**的值中包含一个错误的情况并不常见。</span><span class="sxs-lookup"><span data-stu-id="6edfb-131">If **PR_ATTACH_METHOD** is set to ATTACH_EMBEDDED_MSG, it is not unusual for the value of **PR_ATTACH_DATA_OBJ** to contain an error.</span></span> <span data-ttu-id="6edfb-132">这是因为您和表实施者没有办法同意要返回的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="6edfb-132">This is because you and the table implementer have no way to agree on the type of object to return.</span></span> <span data-ttu-id="6edfb-133">若要检索指向附加邮件的指针, 请使用**IMessage:: OpenAttach**打开附件。</span><span class="sxs-lookup"><span data-stu-id="6edfb-133">To retrieve a pointer to the attached message, open the attachment using **IMessage::OpenAttach**.</span></span> <span data-ttu-id="6edfb-134">然后, 通过调用**IMAPIProp:: OpenProperty**方法访问附件数据。</span><span class="sxs-lookup"><span data-stu-id="6edfb-134">Then access the attachment data by calling its **IMAPIProp::OpenProperty** method.</span></span> <span data-ttu-id="6edfb-135">有关详细信息, 请参阅[IMessage:: OpenAttach](imessage-openattach.md)和[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="6edfb-135">For more information, see [IMessage::OpenAttach](imessage-openattach.md) and [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
    
<span data-ttu-id="6edfb-136">您可以请求以读/写模式或只读模式打开附件。</span><span class="sxs-lookup"><span data-stu-id="6edfb-136">You can request that an attachment is opened in read/write or read-only mode.</span></span> <span data-ttu-id="6edfb-137">只读是默认模式, 许多邮件存储区提供程序在此模式下打开所有附件, 而不考虑客户端请求的是什么。</span><span class="sxs-lookup"><span data-stu-id="6edfb-137">Read-only is the default mode, and many message store providers open all attachments in this mode regardless of what clients request.</span></span> <span data-ttu-id="6edfb-138">传递 MAPI_BEST_ACCESS 标志以请求邮件存储提供程序授予最高级别的访问权限, 然后检索打开附件的**PR_ACCESS_LEVEL**属性, 以确定实际授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="6edfb-138">Pass the MAPI_BEST_ACCESS flag to request that the message store provider grant the highest level of access it can and then retrieve the open attachment's **PR_ACCESS_LEVEL** property to determine the level of access that was actually granted.</span></span> <span data-ttu-id="6edfb-139">有关详细信息, 请参阅**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6edfb-139">For more information, see **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)).</span></span>
  
<span data-ttu-id="6edfb-140">下面的示例演示如何在附件的**PR\_ATTACH_DATA_BIN**属性中打开数据。</span><span class="sxs-lookup"><span data-stu-id="6edfb-140">The following example shows how to open the data in an attachment's **PR\_ATTACH_DATA_BIN** property.</span></span> <span data-ttu-id="6edfb-141">它分配指向两个流的指针: 一个用于文件, 一个用于附件。</span><span class="sxs-lookup"><span data-stu-id="6edfb-141">It allocates pointers to two streams: one for the file and one for the attachment.</span></span> <span data-ttu-id="6edfb-142">**OpenStreamOnFile**函数将以只读模式打开文件流。</span><span class="sxs-lookup"><span data-stu-id="6edfb-142">The **OpenStreamOnFile** function opens the file stream in read-only mode.</span></span> <span data-ttu-id="6edfb-143">对附件的**IMAPIProp:: OpenProperty**方法的调用将以读/写模式打开附件流。</span><span class="sxs-lookup"><span data-stu-id="6edfb-143">The call to the attachment's **IMAPIProp::OpenProperty** method opens the attachment stream in read/write mode.</span></span> <span data-ttu-id="6edfb-144">有关详细信息, 请参阅**PR_ATTACH_DATA_BIN**、 [OpenStreamOnFile](openstreamonfile.md)和[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="6edfb-144">For more information, see **PR_ATTACH_DATA_BIN**, [OpenStreamOnFile](openstreamonfile.md), and [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="6edfb-145">然后, 该代码将文件流中的副本复制到附件流, 并释放这两个流。</span><span class="sxs-lookup"><span data-stu-id="6edfb-145">The code then copies from the file stream to the attachment stream and releases both streams.</span></span>
  
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


