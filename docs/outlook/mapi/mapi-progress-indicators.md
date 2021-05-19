---
title: MAPI 进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 73a99e52-97fe-40f5-af90-52cfd858ab22
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cdfb6898146583b7da9b043eadd3acc09edbf292
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410705"
---
# <a name="mapi-progress-indicators"></a><span data-ttu-id="8a285-103">MAPI 进度指示器</span><span class="sxs-lookup"><span data-stu-id="8a285-103">MAPI Progress Indicators</span></span>

  
  
<span data-ttu-id="8a285-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8a285-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8a285-105">为客户端执行的许多操作可能需要很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="8a285-105">Many of the operations that you perform for clients can take a long time to complete.</span></span> <span data-ttu-id="8a285-106">若要通知客户端长时间操作的进度，可以显示一个指示器，以图形方式显示从操作开始到完成的任何给定时间点的操作已完成部分。</span><span class="sxs-lookup"><span data-stu-id="8a285-106">To inform clients of the progress of a lengthy operation, you can show an indicator that displays graphically the finished portion of an operation at any given point from the start of the operation to its completion.</span></span> <span data-ttu-id="8a285-107">进度指示器显示要完成的总操作百分比。</span><span class="sxs-lookup"><span data-stu-id="8a285-107">The progress indicator shows a percentage of the total operation to be completed.</span></span>
  
<span data-ttu-id="8a285-108">以下方法支持冗长的操作和进度指示器的显示：</span><span class="sxs-lookup"><span data-stu-id="8a285-108">The following methods support lengthy operations and the display of a progress indicator:</span></span>
  
- <span data-ttu-id="8a285-109">[IMAPIFolder：：CopyMessages](imapifolder-copymessages.md)、IMAPIFolder：：CopyFolder、IMAPIFolder：:D eleteMessages、IMAPIFolder：:D eleteFolder、IMAPIFolder：：EmptyFolder 和[IMAPIFolder：：SetReadFlags](imapifolder-setreadflags.md)。 [](imapifolder-copyfolder.md) [](imapifolder-deletemessages.md) [](imapifolder-deletefolder.md) [](imapifolder-emptyfolder.md)</span><span class="sxs-lookup"><span data-stu-id="8a285-109">[IMAPIFolder::CopyMessages](imapifolder-copymessages.md), [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md), [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md), [IMAPIFolder::DeleteFolder](imapifolder-deletefolder.md), [IMAPIFolder::EmptyFolder](imapifolder-emptyfolder.md), and [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md).</span></span>
    
- <span data-ttu-id="8a285-110">[IMAPIProp：：CopyProps](imapiprop-copyprops.md) 和 [IMAPIProp：：CopyTo](imapiprop-copyto.md)。</span><span class="sxs-lookup"><span data-stu-id="8a285-110">[IMAPIProp::CopyProps](imapiprop-copyprops.md) and [IMAPIProp::CopyTo](imapiprop-copyto.md).</span></span>
    
- <span data-ttu-id="8a285-111">[IMAPISupport：:D oCopyProps](imapisupport-docopyprops.md) [、IMAPISupport：:D oCopyTo](imapisupport-docopyto.md) [、IMAPISupport：：CopyFolder](imapisupport-copyfolder.md)和 [IMAPISupport：：CopyMessages](imapisupport-copymessages.md)。</span><span class="sxs-lookup"><span data-stu-id="8a285-111">[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md), [IMAPISupport::DoCopyTo](imapisupport-docopyto.md), [IMAPISupport::CopyFolder](imapisupport-copyfolder.md), and [IMAPISupport::CopyMessages](imapisupport-copymessages.md).</span></span>
    
- <span data-ttu-id="8a285-112">[IMessage：:D eleteAttach](imessage-deleteattach.md)。</span><span class="sxs-lookup"><span data-stu-id="8a285-112">[IMessage::DeleteAttach](imessage-deleteattach.md).</span></span>
    
- <span data-ttu-id="8a285-113">[IABContainer：：CopyEntries](iabcontainer-copyentries.md)。</span><span class="sxs-lookup"><span data-stu-id="8a285-113">[IABContainer::CopyEntries](iabcontainer-copyentries.md).</span></span>
    
<span data-ttu-id="8a285-114">若要显示进度指示器，MAPI 定义进度对象。</span><span class="sxs-lookup"><span data-stu-id="8a285-114">To display a progress indicator, MAPI defines a progress object.</span></span> <span data-ttu-id="8a285-115">Progress 对象实现 [IMAPIProgress ： IUnknown](imapiprogressiunknown.md) 接口，该接口包括用于建立指示器范围和创建显示的方法。</span><span class="sxs-lookup"><span data-stu-id="8a285-115">Progress objects implement the [IMAPIProgress : IUnknown](imapiprogressiunknown.md) interface, an interface that includes methods for establishing the range of the indicator and creating the display.</span></span> <span data-ttu-id="8a285-116">MAPI 提供与某些客户端一样的进度对象实现。</span><span class="sxs-lookup"><span data-stu-id="8a285-116">MAPI provides a progress object implementation as do some clients.</span></span> <span data-ttu-id="8a285-117">您应使用客户端的实现（如果已提供）作为执行该操作的方法的输入参数。</span><span class="sxs-lookup"><span data-stu-id="8a285-117">You should use a client's implementation, if one is supplied, as an input parameter to the method performing the operation.</span></span> <span data-ttu-id="8a285-118">如果客户端传递 NULL 而不是指向进度对象的指针，则通过调用 [IMAPISupport：:D oProgressDialog](imapisupport-doprogressdialog.md) 方法来使用 MAPI 的实现。</span><span class="sxs-lookup"><span data-stu-id="8a285-118">If the client passes NULL instead of a pointer to a progress object, use MAPI's implementation by calling the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8a285-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a285-119">See also</span></span>



[<span data-ttu-id="8a285-120">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="8a285-120">MAPI Service Providers</span></span>](mapi-service-providers.md)

