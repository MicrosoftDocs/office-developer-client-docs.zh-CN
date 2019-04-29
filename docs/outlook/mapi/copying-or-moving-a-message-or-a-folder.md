---
title: 复制或移动邮件或文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72290fd3-00d7-4055-bbfa-0c47b6e0f62d
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: c5e92c44d7078560ed84d72b3477d5cf2e809353
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413498"
---
# <a name="copying-or-moving-a-message-or-a-folder"></a><span data-ttu-id="e3074-103">复制或移动邮件或文件夹</span><span class="sxs-lookup"><span data-stu-id="e3074-103">Copying or moving a message or a folder</span></span>
  
<span data-ttu-id="e3074-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e3074-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e3074-105">客户端可以使用以下四种方法之一来复制或移动邮件或文件夹:</span><span class="sxs-lookup"><span data-stu-id="e3074-105">A client can use one of four methods to copy or move a message or a folder:</span></span>
  
- [<span data-ttu-id="e3074-106">IMAPIFolder::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="e3074-106">IMAPIFolder::CopyFolder</span></span>](imapifolder-copyfolder.md)
    
- [<span data-ttu-id="e3074-107">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="e3074-107">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
    
- [<span data-ttu-id="e3074-108">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="e3074-108">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
    
- [<span data-ttu-id="e3074-109">IMAPIProp::CopyProps</span><span class="sxs-lookup"><span data-stu-id="e3074-109">IMAPIProp::CopyProps</span></span>](imapiprop-copyprops.md)
    
<span data-ttu-id="e3074-110">通过设置适当的标志和参数, 可以对**CopyTo**和**CopyProps**进行操作, 就像**CopyFolder**或**CopyMessages**一样。</span><span class="sxs-lookup"><span data-stu-id="e3074-110">By setting the appropriate flags and parameters, **CopyTo** and **CopyProps** can be made to work just like **CopyFolder** or **CopyMessages**.</span></span> <span data-ttu-id="e3074-111">在决定要调用哪种方法时, 请考虑以下问题:</span><span class="sxs-lookup"><span data-stu-id="e3074-111">Consider the following issues when deciding which method to call:</span></span>
  
- <span data-ttu-id="e3074-112">您是否正在复制或移动文件夹或邮件？</span><span class="sxs-lookup"><span data-stu-id="e3074-112">Are you copying or moving a folder or a message?</span></span>
    
- <span data-ttu-id="e3074-113">您知道要移动或复制的文件夹或邮件需要多少钱？</span><span class="sxs-lookup"><span data-stu-id="e3074-113">How much do you know about the folder or message to be moved or copied?</span></span>
    
- <span data-ttu-id="e3074-114">将移动或复制多少个文件夹或邮件的属性？</span><span class="sxs-lookup"><span data-stu-id="e3074-114">How many of the folder or message's properties will be moved or copied?</span></span>
    
<span data-ttu-id="e3074-115">您可以使用**IMAPIProp**方法复制或移动文件夹或邮件。</span><span class="sxs-lookup"><span data-stu-id="e3074-115">You can use the **IMAPIProp** methods to copy or move either a folder or a message.</span></span> <span data-ttu-id="e3074-116">**IMAPIFolder:: CopyMessages**仅处理邮件;**IMAPIFolder:: CopyFolder**仅处理文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3074-116">**IMAPIFolder::CopyMessages** works with messages only; **IMAPIFolder::CopyFolder** works with folders only.</span></span> 
  
<span data-ttu-id="e3074-117">而使用**IMAPIFolder**方法不需要了解要复制或移动的文件夹或邮件所支持的属性, 但必须有一些知识才能使用**IMAPIProp**方法。</span><span class="sxs-lookup"><span data-stu-id="e3074-117">Whereas using the **IMAPIFolder** methods does not require any knowledge of the properties supported by the folder or message to be copied or moved, you must have some knowledge to use the **IMAPIProp** methods.</span></span> <span data-ttu-id="e3074-118">使用**IMAPIProp:: CopyProps**, 您必须能够明确指定要复制或移动的文件夹或邮件属性。</span><span class="sxs-lookup"><span data-stu-id="e3074-118">With **IMAPIProp::CopyProps**, you must be able to explicitly specify which of the folder or message properties that you want to copy or move.</span></span> <span data-ttu-id="e3074-119">使用**IMAPIProp:: CopyTo**, 除非要复制或移动所有属性, 否则必须明确指定应排除的属性。</span><span class="sxs-lookup"><span data-stu-id="e3074-119">With **IMAPIProp::CopyTo**, unless you want to copy or move all of the properties, you must explicitly specify which ones should be excluded.</span></span> <span data-ttu-id="e3074-120">有关这些方法的详细信息, 请参阅[复制 MAPI 属性](copying-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="e3074-120">For more information about these methods, see [Copying MAPI Properties](copying-mapi-properties.md).</span></span>
  
<span data-ttu-id="e3074-121">要复制或移动的属性的数量可能会影响要使用的方法的决定。</span><span class="sxs-lookup"><span data-stu-id="e3074-121">The number of properties to be copied or moved can affect your decision as to which method to use.</span></span> <span data-ttu-id="e3074-122">如果要复制或移动多封邮件, 请调用**IMAPIFolder:: CopyMessages**。</span><span class="sxs-lookup"><span data-stu-id="e3074-122">If you are copying or moving multiple messages, call **IMAPIFolder::CopyMessages**.</span></span> <span data-ttu-id="e3074-123">另一种选择是调用**IMAPIProp:: CopyProps**以仅复制文件夹的**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e3074-123">An alternate choice is to call **IMAPIProp::CopyProps** to copy only the folder's **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) property.</span></span> <span data-ttu-id="e3074-124">下面的过程演示如何使用**CopyMessages**。</span><span class="sxs-lookup"><span data-stu-id="e3074-124">The following procedure shows how to use **CopyMessages**.</span></span> 
  
### <a name="to-copy-or-move-one-or-more-messages"></a><span data-ttu-id="e3074-125">复制或移动一个或多个邮件</span><span class="sxs-lookup"><span data-stu-id="e3074-125">To copy or move one or more messages</span></span>
  
1. <span data-ttu-id="e3074-126">查找源和目标文件夹的有效条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e3074-126">Locate valid entry identifiers for the source and destination folders.</span></span>
    
2. <span data-ttu-id="e3074-127">通过调用[IMAPISession:: OpenEntry](imapisession-openentry.md)或[IMsgStore:: OpenEntry](imsgstore-openentry.md)并设置 MAPI_MODIFY 标志, 可以在读/写模式下打开这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3074-127">Open these folders in read/write mode by calling either [IMAPISession::OpenEntry](imapisession-openentry.md) or [IMsgStore::OpenEntry](imsgstore-openentry.md) and setting the MAPI_MODIFY flag.</span></span> 
    
3. <span data-ttu-id="e3074-128">检查从**OpenEntry**返回的接口指针是否为**IMAPIFolder**接口指针。</span><span class="sxs-lookup"><span data-stu-id="e3074-128">Check that the interface pointer returned from **OpenEntry** is an **IMAPIFolder** interface pointer.</span></span> <span data-ttu-id="e3074-129">如果不是, 则将其强制转换为 LPMAPIFOLDER 类型。</span><span class="sxs-lookup"><span data-stu-id="e3074-129">If not, cast it to the LPMAPIFOLDER type.</span></span> 
    
4. <span data-ttu-id="e3074-130">创建条目标识符的数组, 表示要复制或移动的一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="e3074-130">Create an array of entry identifiers representing the one or more messages to be copied or moved.</span></span> 
    
5. <span data-ttu-id="e3074-131">使用以下标志集调用**IMAPIFolder:: CopyMessages** :</span><span class="sxs-lookup"><span data-stu-id="e3074-131">Call **IMAPIFolder::CopyMessages** with the following flags set:</span></span> 
    
   - <span data-ttu-id="e3074-132">MESSAGE_MOVE, 如果要执行移动操作。</span><span class="sxs-lookup"><span data-stu-id="e3074-132">MESSAGE_MOVE, if you want to perform a move operation.</span></span> 
    
   - <span data-ttu-id="e3074-133">MESSAGE_DIALOG 并在_ulUIParam_参数中传递窗口句柄 (如果希望文件夹显示进度指示器)。</span><span class="sxs-lookup"><span data-stu-id="e3074-133">MESSAGE_DIALOG and pass a window handle in the  _ulUIParam_ parameter, if you want the folder to show a progress indicator.</span></span> 
    
6. <span data-ttu-id="e3074-134">释放源和目标文件夹的**IMAPIFolder**指针。</span><span class="sxs-lookup"><span data-stu-id="e3074-134">Release the **IMAPIFolder** pointers for the source and destination folders.</span></span> 
    
<span data-ttu-id="e3074-135">如果要将文件夹的完整内容复制到另一个文件夹, 请调用源文件夹的**IMAPIFolder:: CopyFolder**或**IMAPIProp:: CopyTo**方法。</span><span class="sxs-lookup"><span data-stu-id="e3074-135">If you want to copy the complete contents of a folder to another folder, call the source folder's **IMAPIFolder::CopyFolder** or **IMAPIProp::CopyTo** method.</span></span> 
  
<span data-ttu-id="e3074-136">若要复制文件夹的一些属性, 请调用其**IMAPIProp:: CopyProps**方法。</span><span class="sxs-lookup"><span data-stu-id="e3074-136">To copy a few of a folder's properties, call its **IMAPIProp::CopyProps** method.</span></span> <span data-ttu-id="e3074-137">若要复制文件夹的大部分属性, 请调用**IMAPIProp:: CopyTo**。</span><span class="sxs-lookup"><span data-stu-id="e3074-137">To copy most of a folder's properties, call **IMAPIProp::CopyTo**.</span></span> 
  
<span data-ttu-id="e3074-138">例如, 如果要复制文件夹的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性, 您可以选择以下选项:</span><span class="sxs-lookup"><span data-stu-id="e3074-138">For example, if you want to copy a folder's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) and **PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) properties, you have the following options:</span></span>
  
- <span data-ttu-id="e3074-139">调用**IMAPIFolder:: CopyFolder**以复制所有文件夹属性, 然后从新文件夹中删除不需要的属性。</span><span class="sxs-lookup"><span data-stu-id="e3074-139">Call **IMAPIFolder::CopyFolder** to copy all of the folder properties and then delete the unwanted ones from the new folder.</span></span> 
    
- <span data-ttu-id="e3074-140">调用**CopyTo**并排除除**PR_DISPLAY_NAME**和**PR_COMMENT**之外的所有文件夹属性。</span><span class="sxs-lookup"><span data-stu-id="e3074-140">Call **CopyTo** and exclude all of the folder's properties except for **PR_DISPLAY_NAME** and **PR_COMMENT**.</span></span> 
    
- <span data-ttu-id="e3074-141">调用**CopyProps**, 在 include 数组中传递**PR_DISPLAY_NAME**和**PR_COMMENT** 。</span><span class="sxs-lookup"><span data-stu-id="e3074-141">Call **CopyProps**, passing **PR_DISPLAY_NAME** and **PR_COMMENT** in the include array.</span></span> 
    
<span data-ttu-id="e3074-142">在这种情况下, **CopyProps**是最佳选择, 因为它旨在用于复制一小部分属性, 并且是实现最简单的调用。</span><span class="sxs-lookup"><span data-stu-id="e3074-142">In this case, **CopyProps** is the best choice because it is meant to be used to copy a small set of properties and is the easiest call to implement.</span></span> 
  
<span data-ttu-id="e3074-143">若要仅复制或移动文件夹属性, 而不包括邮件, 请调用文件夹的**IMAPIProp:: CopyTo**方法, 并排除以下属性:</span><span class="sxs-lookup"><span data-stu-id="e3074-143">To copy or move only folder properties, without including messages, call the folder's **IMAPIProp::CopyTo** method and exclude the following properties:</span></span> 
  
- <span data-ttu-id="e3074-144">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e3074-144">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>
    
- <span data-ttu-id="e3074-145">**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e3074-145">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>
    
<span data-ttu-id="e3074-146">copy 方法可返回 S_OK, 指示 total success, MAPI_W_PARTIAL_COMPLETION, 指示部分成功或错误。</span><span class="sxs-lookup"><span data-stu-id="e3074-146">The copy methods can return S_OK, indicating total success, MAPI_W_PARTIAL_COMPLETION, indicating partial success, or an error.</span></span> <span data-ttu-id="e3074-147">如果返回 MAPI_W_PARTIAL_COMPLETION, 则使用**HR_FAILED**宏访问更具体的错误。</span><span class="sxs-lookup"><span data-stu-id="e3074-147">If MAPI_W_PARTIAL_COMPLETION is returned, use the **HR_FAILED** macro to access a more specific error.</span></span> <span data-ttu-id="e3074-148">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="e3074-148">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
  
<span data-ttu-id="e3074-149">如果将邮件从一个邮件存储复制到另一个邮件存储, 且不支持 Unicode, 请注意, 由于代码页转换, 信息可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="e3074-149">If you copy messages from one message store to another and Unicode is not supported by both, be aware that information can be lost due to code page conversion.</span></span> <span data-ttu-id="e3074-150">通常情况下, 您无法知道邮件存储区是否支持一种或两种格式, 这样做无法确定是将文本属性复制为 ASCII 字符串, 也不能将其复制为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="e3074-150">Usually you cannot know if the message stores support one or both formats, making it impossible to determine whether to copy text properties as ASCII strings or as Unicode strings.</span></span> <span data-ttu-id="e3074-151">如果你支持 unicode, 请尝试执行 unicode 复制;如果失败, 并出现错误值 MAPI_E_BAD_CHARWIDTH, 请使用 ASCII。</span><span class="sxs-lookup"><span data-stu-id="e3074-151">If you support Unicode, try to perform a Unicode copy; if it fails with the error value MAPI_E_BAD_CHARWIDTH, resort to ASCII.</span></span>
  

