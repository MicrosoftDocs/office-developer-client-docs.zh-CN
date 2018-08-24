---
title: MAPI 进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 73a99e52-97fe-40f5-af90-52cfd858ab22
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8fc39c6d7da0970ee15cdd9dd67bfeef0997d7d1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582866"
---
# <a name="mapi-progress-indicators"></a><span data-ttu-id="60d56-103">MAPI 进度指示器</span><span class="sxs-lookup"><span data-stu-id="60d56-103">MAPI Progress Indicators</span></span>

  
  
<span data-ttu-id="60d56-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="60d56-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="60d56-105">客户端执行的操作的许多花费很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="60d56-105">Many of the operations that you perform for clients can take a long time to complete.</span></span> <span data-ttu-id="60d56-106">通知客户端的较长操作的进度，可以显示在从操作开始到完成任何给定点以图形方式显示操作的完成的部分标记。</span><span class="sxs-lookup"><span data-stu-id="60d56-106">To inform clients of the progress of a lengthy operation, you can show an indicator that displays graphically the finished portion of an operation at any given point from the start of the operation to its completion.</span></span> <span data-ttu-id="60d56-107">进度指示器显示总操作完成的百分比。</span><span class="sxs-lookup"><span data-stu-id="60d56-107">The progress indicator shows a percentage of the total operation to be completed.</span></span>
  
<span data-ttu-id="60d56-108">以下方法支持长时间的操作和显示进度指示器的：</span><span class="sxs-lookup"><span data-stu-id="60d56-108">The following methods support lengthy operations and the display of a progress indicator:</span></span>
  
- <span data-ttu-id="60d56-109">[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)、 [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)、 [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)、 [IMAPIFolder::DeleteFolder](imapifolder-deletefolder.md)、 [IMAPIFolder::EmptyFolder](imapifolder-emptyfolder.md)和[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)。</span><span class="sxs-lookup"><span data-stu-id="60d56-109">[IMAPIFolder::CopyMessages](imapifolder-copymessages.md), [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md), [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md), [IMAPIFolder::DeleteFolder](imapifolder-deletefolder.md), [IMAPIFolder::EmptyFolder](imapifolder-emptyfolder.md), and [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md).</span></span>
    
- <span data-ttu-id="60d56-110">[IMAPIProp::CopyProps](imapiprop-copyprops.md)和[IMAPIProp::CopyTo](imapiprop-copyto.md)。</span><span class="sxs-lookup"><span data-stu-id="60d56-110">[IMAPIProp::CopyProps](imapiprop-copyprops.md) and [IMAPIProp::CopyTo](imapiprop-copyto.md).</span></span>
    
- <span data-ttu-id="60d56-111">[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)、 [IMAPISupport::DoCopyTo](imapisupport-docopyto.md)、 [IMAPISupport::CopyFolder](imapisupport-copyfolder.md)和[IMAPISupport::CopyMessages](imapisupport-copymessages.md)。</span><span class="sxs-lookup"><span data-stu-id="60d56-111">[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md), [IMAPISupport::DoCopyTo](imapisupport-docopyto.md), [IMAPISupport::CopyFolder](imapisupport-copyfolder.md), and [IMAPISupport::CopyMessages](imapisupport-copymessages.md).</span></span>
    
- <span data-ttu-id="60d56-112">[IMessage::DeleteAttach](imessage-deleteattach.md)。</span><span class="sxs-lookup"><span data-stu-id="60d56-112">[IMessage::DeleteAttach](imessage-deleteattach.md).</span></span>
    
- <span data-ttu-id="60d56-113">[IABContainer::CopyEntries](iabcontainer-copyentries.md)。</span><span class="sxs-lookup"><span data-stu-id="60d56-113">[IABContainer::CopyEntries](iabcontainer-copyentries.md).</span></span>
    
<span data-ttu-id="60d56-114">若要显示进度指示器，MAPI 定义进度对象。</span><span class="sxs-lookup"><span data-stu-id="60d56-114">To display a progress indicator, MAPI defines a progress object.</span></span> <span data-ttu-id="60d56-115">进度对象实现[IMAPIProgress: IUnknown](imapiprogressiunknown.md)接口，包含用于建立指示器的范围和创建显示方法的接口。</span><span class="sxs-lookup"><span data-stu-id="60d56-115">Progress objects implement the [IMAPIProgress : IUnknown](imapiprogressiunknown.md) interface, an interface that includes methods for establishing the range of the indicator and creating the display.</span></span> <span data-ttu-id="60d56-116">MAPI 提供了一个进度对象实现如下执行某些客户端。</span><span class="sxs-lookup"><span data-stu-id="60d56-116">MAPI provides a progress object implementation as do some clients.</span></span> <span data-ttu-id="60d56-117">如果一个，作为提供执行操作的方法的输入参数，您应使用客户端的实现。</span><span class="sxs-lookup"><span data-stu-id="60d56-117">You should use a client's implementation, if one is supplied, as an input parameter to the method performing the operation.</span></span> <span data-ttu-id="60d56-118">如果客户端将 NULL 而不是一个指针传递给进度对象，通过调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法使用 MAPI 的实现。</span><span class="sxs-lookup"><span data-stu-id="60d56-118">If the client passes NULL instead of a pointer to a progress object, use MAPI's implementation by calling the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="60d56-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60d56-119">See also</span></span>



[<span data-ttu-id="60d56-120">MAPI 服务提供商</span><span class="sxs-lookup"><span data-stu-id="60d56-120">MAPI Service Providers</span></span>](mapi-service-providers.md)

