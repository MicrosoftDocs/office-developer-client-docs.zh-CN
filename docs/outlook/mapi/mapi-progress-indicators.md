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
# <a name="mapi-progress-indicators"></a>MAPI 进度指示器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您对客户端执行的许多操作可能需要很长时间才能完成。 若要将较长操作的进度通知客户端, 您可以显示指示器, 以图形方式显示操作从操作开始到完成的任意给定点处的已完成部分。 进度指示器显示要完成的全部操作的百分比。
  
以下方法支持漫长的操作和进度指示器的显示:
  
- [IMAPIFolder:: CopyMessages](imapifolder-copymessages.md), [IMAPIFolder:: CopyFolder](imapifolder-copyfolder.md), [IMAPIFolder::D eletemessages](imapifolder-deletemessages.md), [IMAPIFolder::D eletefolder](imapifolder-deletefolder.md), [IMAPIFolder:: EmptyFolder](imapifolder-emptyfolder.md), and [IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)。
    
- [IMAPIProp:: CopyProps](imapiprop-copyprops.md)和[IMAPIProp:: CopyTo](imapiprop-copyto.md)。
    
- [IMAPISupport::D ocopyprops](imapisupport-docopyprops.md)、 [IMAPISupport::D ocopyto](imapisupport-docopyto.md)、 [IMAPISupport:: CopyFolder](imapisupport-copyfolder.md)和[IMAPISupport:: CopyMessages](imapisupport-copymessages.md)。
    
- [IMessage::D eleteattach](imessage-deleteattach.md)。
    
- [IABContainer:: CopyEntries](iabcontainer-copyentries.md)。
    
若要显示进度指示器, MAPI 将定义进度对象。 进度对象实现[IMAPIProgress: IUnknown](imapiprogressiunknown.md)接口, 它是一个接口, 其中包含用于建立指示器的范围并创建显示的方法。 MAPI 提供了一些客户端的进度对象实现。 如果提供了客户端的实现, 则应使用它作为执行该操作的方法的输入参数。 如果客户端传递的是 NULL 而不是指向进度对象的指针, 请通过调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)方法来使用 MAPI 的实现。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

