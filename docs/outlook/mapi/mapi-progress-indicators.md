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
# <a name="mapi-progress-indicators"></a>MAPI 进度指示器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端执行的操作的许多花费很长时间才能完成。 通知客户端的较长操作的进度，可以显示在从操作开始到完成任何给定点以图形方式显示操作的完成的部分标记。 进度指示器显示总操作完成的百分比。
  
以下方法支持长时间的操作和显示进度指示器的：
  
- [IMAPIFolder::CopyMessages](imapifolder-copymessages.md)、 [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)、 [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)、 [IMAPIFolder::DeleteFolder](imapifolder-deletefolder.md)、 [IMAPIFolder::EmptyFolder](imapifolder-emptyfolder.md)和[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)。
    
- [IMAPIProp::CopyProps](imapiprop-copyprops.md)和[IMAPIProp::CopyTo](imapiprop-copyto.md)。
    
- [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)、 [IMAPISupport::DoCopyTo](imapisupport-docopyto.md)、 [IMAPISupport::CopyFolder](imapisupport-copyfolder.md)和[IMAPISupport::CopyMessages](imapisupport-copymessages.md)。
    
- [IMessage::DeleteAttach](imessage-deleteattach.md)。
    
- [IABContainer::CopyEntries](iabcontainer-copyentries.md)。
    
若要显示进度指示器，MAPI 定义进度对象。 进度对象实现[IMAPIProgress: IUnknown](imapiprogressiunknown.md)接口，包含用于建立指示器的范围和创建显示方法的接口。 MAPI 提供了一个进度对象实现如下执行某些客户端。 如果一个，作为提供执行操作的方法的输入参数，您应使用客户端的实现。 如果客户端将 NULL 而不是一个指针传递给进度对象，通过调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法使用 MAPI 的实现。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

