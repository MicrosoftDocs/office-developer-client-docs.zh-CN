---
title: 复制或移动邮件或文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72290fd3-00d7-4055-bbfa-0c47b6e0f62d
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: c5e92c44d7078560ed84d72b3477d5cf2e809353
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413498"
---
# <a name="copying-or-moving-a-message-or-a-folder"></a><span data-ttu-id="f5f8e-103">复制或移动邮件或文件夹</span><span class="sxs-lookup"><span data-stu-id="f5f8e-103">Copying or moving a message or a folder</span></span>
  
<span data-ttu-id="f5f8e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f5f8e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f5f8e-105">客户端可以使用以下四种方法之一复制或移动邮件或文件夹：</span><span class="sxs-lookup"><span data-stu-id="f5f8e-105">A client can use one of four methods to copy or move a message or a folder:</span></span>
  
- [<span data-ttu-id="f5f8e-106">IMAPIFolder::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="f5f8e-106">IMAPIFolder::CopyFolder</span></span>](imapifolder-copyfolder.md)
    
- [<span data-ttu-id="f5f8e-107">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="f5f8e-107">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
    
- [<span data-ttu-id="f5f8e-108">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="f5f8e-108">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
    
- [<span data-ttu-id="f5f8e-109">IMAPIProp::CopyProps</span><span class="sxs-lookup"><span data-stu-id="f5f8e-109">IMAPIProp::CopyProps</span></span>](imapiprop-copyprops.md)
    
<span data-ttu-id="f5f8e-110">通过设置适当的标志和参数 **，CopyTo** 和 **CopyProps** 可以像 **CopyFolder** 或 **CopyMessages** 一样工作。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-110">By setting the appropriate flags and parameters, **CopyTo** and **CopyProps** can be made to work just like **CopyFolder** or **CopyMessages**.</span></span> <span data-ttu-id="f5f8e-111">在决定调用哪种方法时，请考虑以下问题：</span><span class="sxs-lookup"><span data-stu-id="f5f8e-111">Consider the following issues when deciding which method to call:</span></span>
  
- <span data-ttu-id="f5f8e-112">复制或移动文件夹还是邮件？</span><span class="sxs-lookup"><span data-stu-id="f5f8e-112">Are you copying or moving a folder or a message?</span></span>
    
- <span data-ttu-id="f5f8e-113">您有多少关于要移动或复制的文件夹或邮件的信息？</span><span class="sxs-lookup"><span data-stu-id="f5f8e-113">How much do you know about the folder or message to be moved or copied?</span></span>
    
- <span data-ttu-id="f5f8e-114">将移动或复制多少文件夹或邮件属性？</span><span class="sxs-lookup"><span data-stu-id="f5f8e-114">How many of the folder or message's properties will be moved or copied?</span></span>
    
<span data-ttu-id="f5f8e-115">可以使用 **IMAPIProp** 方法复制或移动文件夹或邮件。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-115">You can use the **IMAPIProp** methods to copy or move either a folder or a message.</span></span> <span data-ttu-id="f5f8e-116">**IMAPIFolder：：CopyMessages** 仅适用于消息; **IMAPIFolder：：CopyFolder** 仅适用于文件夹。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-116">**IMAPIFolder::CopyMessages** works with messages only; **IMAPIFolder::CopyFolder** works with folders only.</span></span> 
  
<span data-ttu-id="f5f8e-117">虽然使用 **IMAPIFolder** 方法不需要任何有关要复制或移动的文件夹或邮件支持的属性的知识，但您必须了解一些使用 **IMAPIProp** 方法的知识。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-117">Whereas using the **IMAPIFolder** methods does not require any knowledge of the properties supported by the folder or message to be copied or moved, you must have some knowledge to use the **IMAPIProp** methods.</span></span> <span data-ttu-id="f5f8e-118">使用 **IMAPIProp：：CopyProps，** 必须能够明确指定要复制或移动的文件夹或邮件属性。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-118">With **IMAPIProp::CopyProps**, you must be able to explicitly specify which of the folder or message properties that you want to copy or move.</span></span> <span data-ttu-id="f5f8e-119">使用 **IMAPIProp：：CopyTo**，除非要复制或移动所有属性，否则必须明确指定应排除哪些属性。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-119">With **IMAPIProp::CopyTo**, unless you want to copy or move all of the properties, you must explicitly specify which ones should be excluded.</span></span> <span data-ttu-id="f5f8e-120">有关这些方法详细信息，请参阅复制 [MAPI 属性](copying-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-120">For more information about these methods, see [Copying MAPI Properties](copying-mapi-properties.md).</span></span>
  
<span data-ttu-id="f5f8e-121">要复制或移动的属性数可能会影响有关使用哪种方法的决定。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-121">The number of properties to be copied or moved can affect your decision as to which method to use.</span></span> <span data-ttu-id="f5f8e-122">如果要复制或移动多个消息，请调用 **IMAPIFolder：：CopyMessages**。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-122">If you are copying or moving multiple messages, call **IMAPIFolder::CopyMessages**.</span></span> <span data-ttu-id="f5f8e-123">另一种选择是调用 **IMAPIProp：：CopyProps** 以仅复制文件夹的 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-123">An alternate choice is to call **IMAPIProp::CopyProps** to copy only the folder's **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) property.</span></span> <span data-ttu-id="f5f8e-124">以下过程演示如何使用 **CopyMessages**。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-124">The following procedure shows how to use **CopyMessages**.</span></span> 
  
### <a name="to-copy-or-move-one-or-more-messages"></a><span data-ttu-id="f5f8e-125">复制或移动一个或多个邮件</span><span class="sxs-lookup"><span data-stu-id="f5f8e-125">To copy or move one or more messages</span></span>
  
1. <span data-ttu-id="f5f8e-126">查找源和目标文件夹的有效条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-126">Locate valid entry identifiers for the source and destination folders.</span></span>
    
2. <span data-ttu-id="f5f8e-127">通过调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 或 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 并设置 MAPI_MODIFY 标志，以读/写模式打开这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-127">Open these folders in read/write mode by calling either [IMAPISession::OpenEntry](imapisession-openentry.md) or [IMsgStore::OpenEntry](imsgstore-openentry.md) and setting the MAPI_MODIFY flag.</span></span> 
    
3. <span data-ttu-id="f5f8e-128">检查从 **OpenEntry** 返回的接口指针是 **IMAPIFolder** 接口指针。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-128">Check that the interface pointer returned from **OpenEntry** is an **IMAPIFolder** interface pointer.</span></span> <span data-ttu-id="f5f8e-129">如果没有，请强制转换到 LPMAPIFOLDER 类型。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-129">If not, cast it to the LPMAPIFOLDER type.</span></span> 
    
4. <span data-ttu-id="f5f8e-130">创建一个条目标识符数组，该数组代表要复制或移动的一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-130">Create an array of entry identifiers representing the one or more messages to be copied or moved.</span></span> 
    
5. <span data-ttu-id="f5f8e-131">调用 **设置了以下标志的 IMAPIFolder：：CopyMessages：**</span><span class="sxs-lookup"><span data-stu-id="f5f8e-131">Call **IMAPIFolder::CopyMessages** with the following flags set:</span></span> 
    
   - <span data-ttu-id="f5f8e-132">MESSAGE_MOVE，如果要执行移动操作。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-132">MESSAGE_MOVE, if you want to perform a move operation.</span></span> 
    
   - <span data-ttu-id="f5f8e-133">MESSAGE_DIALOG  _ulUIParam_ 参数中指定并传递窗口句柄（如果希望文件夹显示进度指示器）。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-133">MESSAGE_DIALOG and pass a window handle in the  _ulUIParam_ parameter, if you want the folder to show a progress indicator.</span></span> 
    
6. <span data-ttu-id="f5f8e-134">释放源文件夹和目标文件夹的 **IMAPIFolder** 指针。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-134">Release the **IMAPIFolder** pointers for the source and destination folders.</span></span> 
    
<span data-ttu-id="f5f8e-135">如果要将文件夹的完整内容复制到另一个文件夹，请调用源文件夹的 **IMAPIFolder：：CopyFolder** 或 **IMAPIProp：：CopyTo** 方法。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-135">If you want to copy the complete contents of a folder to another folder, call the source folder's **IMAPIFolder::CopyFolder** or **IMAPIProp::CopyTo** method.</span></span> 
  
<span data-ttu-id="f5f8e-136">若要复制文件夹的一些属性，请调用 **其 IMAPIProp：：CopyProps** 方法。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-136">To copy a few of a folder's properties, call its **IMAPIProp::CopyProps** method.</span></span> <span data-ttu-id="f5f8e-137">若要复制大多数文件夹的属性，请调用 **IMAPIProp：：CopyTo**。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-137">To copy most of a folder's properties, call **IMAPIProp::CopyTo**.</span></span> 
  
<span data-ttu-id="f5f8e-138">例如，如果要复制文件夹的 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和 **PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性，则有以下选项：</span><span class="sxs-lookup"><span data-stu-id="f5f8e-138">For example, if you want to copy a folder's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) and **PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) properties, you have the following options:</span></span>
  
- <span data-ttu-id="f5f8e-139">调用 **IMAPIFolder：：CopyFolder** 复制所有文件夹属性，然后从新文件夹中删除不需要的属性。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-139">Call **IMAPIFolder::CopyFolder** to copy all of the folder properties and then delete the unwanted ones from the new folder.</span></span> 
    
- <span data-ttu-id="f5f8e-140">调用 **CopyTo** 并排除文件夹的所有属性，PR_DISPLAY_NAME **和\*\*\*\*PR_COMMENT**。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-140">Call **CopyTo** and exclude all of the folder's properties except for **PR_DISPLAY_NAME** and **PR_COMMENT**.</span></span> 
    
- <span data-ttu-id="f5f8e-141">调用 **CopyProps**，在 **include** PR_DISPLAY_NAME **PR_COMMENT** 和 PR_COMMENT。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-141">Call **CopyProps**, passing **PR_DISPLAY_NAME** and **PR_COMMENT** in the include array.</span></span> 
    
<span data-ttu-id="f5f8e-142">在这种情况下 **，CopyProps** 是最佳选择，因为它用于复制一小组属性，也是要实现的最简单调用。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-142">In this case, **CopyProps** is the best choice because it is meant to be used to copy a small set of properties and is the easiest call to implement.</span></span> 
  
<span data-ttu-id="f5f8e-143">若要仅复制或移动文件夹属性（不包括消息），请调用文件夹的 **IMAPIProp：：CopyTo** 方法，并排除以下属性：</span><span class="sxs-lookup"><span data-stu-id="f5f8e-143">To copy or move only folder properties, without including messages, call the folder's **IMAPIProp::CopyTo** method and exclude the following properties:</span></span> 
  
- <span data-ttu-id="f5f8e-144">**PR_CONTAINER_CONTENTS (** [PidTagContainerContents)](pidtagcontainercontents-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="f5f8e-144">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>
    
- <span data-ttu-id="f5f8e-145">**PR_FOLDER_ASSOCIATED_CONTENTS (** [PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="f5f8e-145">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>
    
<span data-ttu-id="f5f8e-146">复制方法可以返回S_OK，指示总成功、MAPI_W_PARTIAL_COMPLETION、指示部分成功或错误。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-146">The copy methods can return S_OK, indicating total success, MAPI_W_PARTIAL_COMPLETION, indicating partial success, or an error.</span></span> <span data-ttu-id="f5f8e-147">如果MAPI_W_PARTIAL_COMPLETION，请使用 HR_FAILED **宏访问** 更具体的错误。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-147">If MAPI_W_PARTIAL_COMPLETION is returned, use the **HR_FAILED** macro to access a more specific error.</span></span> <span data-ttu-id="f5f8e-148">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-148">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
  
<span data-ttu-id="f5f8e-149">如果将邮件从一个邮件存储复制到另一个邮件存储，但 Unicode 不受两者支持，请注意，由于代码页转换，信息可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-149">If you copy messages from one message store to another and Unicode is not supported by both, be aware that information can be lost due to code page conversion.</span></span> <span data-ttu-id="f5f8e-150">通常，您不知道邮件存储是否支持一种或两种格式，因此无法确定是复制文本属性为 ASCII 字符串还是 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-150">Usually you cannot know if the message stores support one or both formats, making it impossible to determine whether to copy text properties as ASCII strings or as Unicode strings.</span></span> <span data-ttu-id="f5f8e-151">如果支持 Unicode，请尝试执行 Unicode 副本;如果失败，错误值MAPI_E_BAD_CHARWIDTH ASCII。</span><span class="sxs-lookup"><span data-stu-id="f5f8e-151">If you support Unicode, try to perform a Unicode copy; if it fails with the error value MAPI_E_BAD_CHARWIDTH, resort to ASCII.</span></span>
  

