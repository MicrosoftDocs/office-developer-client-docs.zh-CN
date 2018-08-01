---
title: 复制或移动邮件或文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72290fd3-00d7-4055-bbfa-0c47b6e0f62d
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 26fe135da93e0f5f94d9f7d264453b74f97a518b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774725"
---
# <a name="copying-or-moving-a-message-or-a-folder"></a><span data-ttu-id="a0b06-103">复制或移动邮件或文件夹</span><span class="sxs-lookup"><span data-stu-id="a0b06-103">Copying or moving a message or a folder</span></span>
  
<span data-ttu-id="a0b06-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a0b06-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a0b06-105">客户端可以使用四种方法之一来复制或移动邮件或文件夹：</span><span class="sxs-lookup"><span data-stu-id="a0b06-105">A client can use one of four methods to copy or move a message or a folder:</span></span>
  
- [<span data-ttu-id="a0b06-106">IMAPIFolder::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="a0b06-106">IMAPIFolder::CopyFolder</span></span>](imapifolder-copyfolder.md)
    
- [<span data-ttu-id="a0b06-107">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="a0b06-107">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
    
- [<span data-ttu-id="a0b06-108">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="a0b06-108">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
    
- [<span data-ttu-id="a0b06-109">IMAPIProp::CopyProps</span><span class="sxs-lookup"><span data-stu-id="a0b06-109">IMAPIProp::CopyProps</span></span>](imapiprop-copyprops.md)
    
<span data-ttu-id="a0b06-110">通过设置的相应标志和参数，可以进行**CopyTo**和**CopyProps**一样**CopyFolder**或**CopyMessages**工作。</span><span class="sxs-lookup"><span data-stu-id="a0b06-110">By setting the appropriate flags and parameters, **CopyTo** and **CopyProps** can be made to work just like **CopyFolder** or **CopyMessages**.</span></span> <span data-ttu-id="a0b06-111">在决定哪种方法来调用时，请考虑以下问题：</span><span class="sxs-lookup"><span data-stu-id="a0b06-111">Consider the following issues when deciding which method to call:</span></span>
  
- <span data-ttu-id="a0b06-112">您所复制或移动的文件夹或一条消息？</span><span class="sxs-lookup"><span data-stu-id="a0b06-112">Are you copying or moving a folder or a message?</span></span>
    
- <span data-ttu-id="a0b06-113">多少有关邮件移动或复制的文件夹知道？</span><span class="sxs-lookup"><span data-stu-id="a0b06-113">How much do you know about the folder or message to be moved or copied?</span></span>
    
- <span data-ttu-id="a0b06-114">文件夹的数量或将移动或复制邮件的属性？</span><span class="sxs-lookup"><span data-stu-id="a0b06-114">How many of the folder or message's properties will be moved or copied?</span></span>
    
<span data-ttu-id="a0b06-115">**IMAPIProp**方法可用于复制或移动的文件夹或一条消息。</span><span class="sxs-lookup"><span data-stu-id="a0b06-115">You can use the **IMAPIProp** methods to copy or move either a folder or a message.</span></span> <span data-ttu-id="a0b06-116">**IMAPIFolder::CopyMessages**处理邮件仅;与文件夹仅适用于**IMAPIFolder::CopyFolder** 。</span><span class="sxs-lookup"><span data-stu-id="a0b06-116">**IMAPIFolder::CopyMessages** works with messages only; **IMAPIFolder::CopyFolder** works with folders only.</span></span> 
  
<span data-ttu-id="a0b06-117">而使用**IMAPIFolder**方法不需要任何知识支持的邮件复制或移动的文件夹的属性，您必须具有一些知识使用**IMAPIProp**方法。</span><span class="sxs-lookup"><span data-stu-id="a0b06-117">Whereas using the **IMAPIFolder** methods does not require any knowledge of the properties supported by the folder or message to be copied or moved, you must have some knowledge to use the **IMAPIProp** methods.</span></span> <span data-ttu-id="a0b06-118">**IMAPIProp::CopyProps**，您必须能够显式指定其要复制或移动的文件夹或邮件属性。</span><span class="sxs-lookup"><span data-stu-id="a0b06-118">With **IMAPIProp::CopyProps**, you must be able to explicitly specify which of the folder or message properties that you want to copy or move.</span></span> <span data-ttu-id="a0b06-119">与**IMAPIProp::CopyTo**，除非您想要复制或移动的所有属性，必须明确指定应排除哪些功能。</span><span class="sxs-lookup"><span data-stu-id="a0b06-119">With **IMAPIProp::CopyTo**, unless you want to copy or move all of the properties, you must explicitly specify which ones should be excluded.</span></span> <span data-ttu-id="a0b06-120">有关这些方法的详细信息，请参阅[复制 MAPI 属性](copying-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="a0b06-120">For more information about these methods, see [Copying MAPI Properties](copying-mapi-properties.md).</span></span>
  
<span data-ttu-id="a0b06-121">要复制或移动的属性数会影响您决定使用哪种方法。</span><span class="sxs-lookup"><span data-stu-id="a0b06-121">The number of properties to be copied or moved can affect your decision as to which method to use.</span></span> <span data-ttu-id="a0b06-122">如果您正在复制或移动多个邮件，呼叫**IMAPIFolder::CopyMessages**。</span><span class="sxs-lookup"><span data-stu-id="a0b06-122">If you are copying or moving multiple messages, call **IMAPIFolder::CopyMessages**.</span></span> <span data-ttu-id="a0b06-123">备用选择是将调用**IMAPIProp::CopyProps**复制仅文件夹的**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a0b06-123">An alternate choice is to call **IMAPIProp::CopyProps** to copy only the folder's **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) property.</span></span> <span data-ttu-id="a0b06-124">下面的过程演示如何使用**CopyMessages**。</span><span class="sxs-lookup"><span data-stu-id="a0b06-124">The following procedure shows how to use **CopyMessages**.</span></span> 
  
### <a name="to-copy-or-move-one-or-more-messages"></a><span data-ttu-id="a0b06-125">复制或移动一个或多个邮件</span><span class="sxs-lookup"><span data-stu-id="a0b06-125">To copy or move one or more messages</span></span>
  
1. <span data-ttu-id="a0b06-126">找到的源和目标文件夹的有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="a0b06-126">Locate valid entry identifiers for the source and destination folders.</span></span>
    
2. <span data-ttu-id="a0b06-127">通过调用[IMAPISession::OpenEntry](imapisession-openentry.md)或[IMsgStore::OpenEntry](imsgstore-openentry.md)并设置 MAPI_MODIFY 标志以读/写模式打开这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0b06-127">Open these folders in read/write mode by calling either [IMAPISession::OpenEntry](imapisession-openentry.md) or [IMsgStore::OpenEntry](imsgstore-openentry.md) and setting the MAPI_MODIFY flag.</span></span> 
    
3. <span data-ttu-id="a0b06-128">检查**OpenEntry**从返回的接口指针是**IMAPIFolder**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="a0b06-128">Check that the interface pointer returned from **OpenEntry** is an **IMAPIFolder** interface pointer.</span></span> <span data-ttu-id="a0b06-129">否则，将其转换为 LPMAPIFOLDER 类型。</span><span class="sxs-lookup"><span data-stu-id="a0b06-129">If not, cast it to the LPMAPIFOLDER type.</span></span> 
    
4. <span data-ttu-id="a0b06-130">创建表示一个或多个邮件复制或移动的项标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="a0b06-130">Create an array of entry identifiers representing the one or more messages to be copied or moved.</span></span> 
    
5. <span data-ttu-id="a0b06-131">设置了以下 flags 呼叫**IMAPIFolder::CopyMessages** :</span><span class="sxs-lookup"><span data-stu-id="a0b06-131">Call **IMAPIFolder::CopyMessages** with the following flags set:</span></span> 
    
   - <span data-ttu-id="a0b06-132">MESSAGE_MOVE，如果您想要执行移动操作。</span><span class="sxs-lookup"><span data-stu-id="a0b06-132">MESSAGE_MOVE, if you want to perform a move operation.</span></span> 
    
   - <span data-ttu-id="a0b06-133">MESSAGE_DIALOG 并传递一个窗口中的处理_ulUIParam_参数，如果您想要显示进度指示器的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0b06-133">MESSAGE_DIALOG and pass a window handle in the  _ulUIParam_ parameter, if you want the folder to show a progress indicator.</span></span> 
    
6. <span data-ttu-id="a0b06-134">发行版的源和目标文件夹的**IMAPIFolder**指针。</span><span class="sxs-lookup"><span data-stu-id="a0b06-134">Release the **IMAPIFolder** pointers for the source and destination folders.</span></span> 
    
<span data-ttu-id="a0b06-135">如果您想要将某个文件夹的完整内容复制到另一个文件夹，调用源文件夹的**IMAPIFolder::CopyFolder**或**IMAPIProp::CopyTo**方法。</span><span class="sxs-lookup"><span data-stu-id="a0b06-135">If you want to copy the complete contents of a folder to another folder, call the source folder's **IMAPIFolder::CopyFolder** or **IMAPIProp::CopyTo** method.</span></span> 
  
<span data-ttu-id="a0b06-136">若要将复制几个文件夹的属性，请调用其**IMAPIProp::CopyProps**方法。</span><span class="sxs-lookup"><span data-stu-id="a0b06-136">To copy a few of a folder's properties, call its **IMAPIProp::CopyProps** method.</span></span> <span data-ttu-id="a0b06-137">若要将复制的大多数某个文件夹的属性，请调用**IMAPIProp::CopyTo**。</span><span class="sxs-lookup"><span data-stu-id="a0b06-137">To copy most of a folder's properties, call **IMAPIProp::CopyTo**.</span></span> 
  
<span data-ttu-id="a0b06-138">例如，如果您想要复制的文件夹**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性，您具有以下选项：</span><span class="sxs-lookup"><span data-stu-id="a0b06-138">For example, if you want to copy a folder's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) and **PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) properties, you have the following options:</span></span>
  
- <span data-ttu-id="a0b06-139">调用**IMAPIFolder::CopyFolder**复制的所有文件夹属性，然后删除不需要的新文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a0b06-139">Call **IMAPIFolder::CopyFolder** to copy all of the folder properties and then delete the unwanted ones from the new folder.</span></span> 
    
- <span data-ttu-id="a0b06-140">调用**CopyTo**和排除所有除**PR_DISPLAY_NAME**和**PR_COMMENT**文件夹的属性。</span><span class="sxs-lookup"><span data-stu-id="a0b06-140">Call **CopyTo** and exclude all of the folder's properties except for **PR_DISPLAY_NAME** and **PR_COMMENT**.</span></span> 
    
- <span data-ttu-id="a0b06-141">调用**CopyProps**， **PR_DISPLAY_NAME**和**PR_COMMENT**传递包含数组中。</span><span class="sxs-lookup"><span data-stu-id="a0b06-141">Call **CopyProps**, passing **PR_DISPLAY_NAME** and **PR_COMMENT** in the include array.</span></span> 
    
<span data-ttu-id="a0b06-142">在这种情况下， **CopyProps**是最佳选择，因为它为了可用于将复制一小组属性和是最简单的呼叫，以实现。</span><span class="sxs-lookup"><span data-stu-id="a0b06-142">In this case, **CopyProps** is the best choice because it is meant to be used to copy a small set of properties and is the easiest call to implement.</span></span> 
  
<span data-ttu-id="a0b06-143">若要复制或移动仅文件夹属性中，不包括消息的情况下，调用该文件夹的**IMAPIProp::CopyTo**方法并不包括以下属性：</span><span class="sxs-lookup"><span data-stu-id="a0b06-143">To copy or move only folder properties, without including messages, call the folder's **IMAPIProp::CopyTo** method and exclude the following properties:</span></span> 
  
- <span data-ttu-id="a0b06-144">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a0b06-144">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>
    
- <span data-ttu-id="a0b06-145">**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a0b06-145">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>
    
<span data-ttu-id="a0b06-146">复制方法可以返回 S_OK，指示总成功，MAPI_W_PARTIAL_COMPLETION，指示部分成功或错误。</span><span class="sxs-lookup"><span data-stu-id="a0b06-146">The copy methods can return S_OK, indicating total success, MAPI_W_PARTIAL_COMPLETION, indicating partial success, or an error.</span></span> <span data-ttu-id="a0b06-147">如果返回 MAPI_W_PARTIAL_COMPLETION，使用**HR_FAILED**宏访问更具体的错误。</span><span class="sxs-lookup"><span data-stu-id="a0b06-147">If MAPI_W_PARTIAL_COMPLETION is returned, use the **HR_FAILED** macro to access a more specific error.</span></span> <span data-ttu-id="a0b06-148">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="a0b06-148">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
  
<span data-ttu-id="a0b06-149">如果将消息从一个消息存储库复制到另一个和 Unicode 不支持这二者，则应注意的信息可能丢失由于代码页转换。</span><span class="sxs-lookup"><span data-stu-id="a0b06-149">If you copy messages from one message store to another and Unicode is not supported by both, be aware that information can be lost due to code page conversion.</span></span> <span data-ttu-id="a0b06-150">通常您无法知道是否消息存储库支持一种或两个格式，使其无法确定是否将复制文本属性作为字符串 ASCII 或 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="a0b06-150">Usually you cannot know if the message stores support one or both formats, making it impossible to determine whether to copy text properties as ASCII strings or as Unicode strings.</span></span> <span data-ttu-id="a0b06-151">如果您支持 Unicode，尝试执行 Unicode 复制;如果失败的错误值 MAPI_E_BAD_CHARWIDTH，，借助 ASCII。</span><span class="sxs-lookup"><span data-stu-id="a0b06-151">If you support Unicode, try to perform a Unicode copy; if it fails with the error value MAPI_E_BAD_CHARWIDTH, resort to ASCII.</span></span>
  

