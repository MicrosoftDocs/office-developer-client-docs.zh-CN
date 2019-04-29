---
title: IMAPIFolderCopyMessages
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CopyMessages
api_type:
- COM
ms.assetid: 4c7d2110-3fcb-4b9f-bf20-1dc1a611161d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21aa28e1a2c11ee7361fb4921f8d527b3e3ceb44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424453"
---
# <a name="imapifoldercopymessages"></a>IMAPIFolder::CopyMessages

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制或移动一个或多个邮件。
  
```cpp
HRESULT CopyMessages(
  LPENTRYLIST lpMsgList,
  LPCIID lpInterface,
  LPVOID lpDestFolder,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpMsgList_
  
> 实时一个指针, 指向标识要复制或移动的邮件的[ENTRYLIST](entrylist.md)结构的数组。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问_lpDestFolder_参数指向的目标文件夹的接口。 在返回标准文件夹接口的服务提供程序中传递 NULL 结果, [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。 客户端必须传递 NULL。 其他调用方可以将_lpInterface_参数设置为 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 或 IID_IMAPIFolder。 
    
 _lpDestFolder_
  
> 实时指向用于接收已复制或移动的邮件的打开文件夹的指针。
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。 _ulUIParam_参数将被忽略, 除非客户端在_ulFlags_参数中设置 MESSAGE_DIALOG 标志并在_lpProgress_参数中传递 NULL。 
    
 _lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。 除非在_ulFlags_中设置了 MESSAGE_DIALOG 标志, 否则_lpProgress_参数将被忽略。
    
 _ulFlags_
  
> 实时用于控制如何完成复制或移动操作的标志的位掩码。 可以设置以下标志:
    
MAPI_DECLINE_OK 
  
> 通知邮件存储提供程序在通过调用支持对象的 IMAPISupport 来实现**IMAPIFolder:: CopyMessages**时立即返回 MAPI_E_DECLINE_COPY: [:D ocopyto](imapisupport-docopyto.md) or [IMAPISupport::D ocopyprops](imapisupport-docopyprops.md)方法。 
    
MESSAGE_DIALOG 
  
> 在操作继续时显示进度指示器。
    
MESSAGE_MOVE 
  
> 要移动而不是复制的邮件。 如果未设置 MESSAGE_MOVE, 则会复制邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动邮件。
    
MAPI_E_DECLINE_COPY 
  
> 提供程序通过调用支持对象方法来实现此方法, 并且调用方已传递 MAPI_DECLINE_OK 标志。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 呼叫成功, 但未成功复制或移动所有条目。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

**IMAPIFolder:: CopyMessages**方法将邮件复制或移动到另一个文件夹。 
  
可以移动或复制以读/写权限打开的邮件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果不使用[IMAPISupport:: CopyMessages](imapisupport-copymessages.md)方法将邮件复制到另一个邮件存储区, 则必须先调用[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)并设置 GENERATE_RECEIPT_ONLY 标志。 接收邮件存储不负责为复制或移动的邮件生成阅读报告。 如果要调用**IMAPISupport:: CopyMessages**实现**IMAPIFolder:: CopyMessages**, 请勿调用**SetReadFlags**;MAPI 将呼叫它。 
  
您的实现可以按任何顺序移动或复制邮件, 并以任何顺序生成阅读状态报告。 也就是说, 您可以在生成任何读取状态报告或在实现开始复制操作之前发送报告之前完成邮件复制。 但是, 无论副本是否成功, 都应将阅读报告发送给所有要复制的邮件。
  
当复制或移动操作涉及多封邮件时, 请尽可能完全地执行该操作。 请勿提前停止操作, 除非发生超出控制范围的故障 (如内存不足、磁盘空间不足或邮件存储区损坏)。
  
请尝试在移动或复制操作中维护条目标识符。 您还应保留条目标识符, 尽管这不是必需的。
  
移动或复制邮件时发送通知, 以便客户端 forewarned 其对邮件 " [IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法" 的调用可能会失败。 
  
请勿在复制或移动操作中包括邮件的状态。 移动或复制邮件状态会对性能产生重大影响。
  
## <a name="notes-to-callers"></a>给调用方的说明

使用**IMAPIFolder:: CopyMessages**填充搜索结果文件夹, 其中邮件通常按父文件夹进行分组。 
  
在下列情况下, 需要这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**IMAPIFolder:: CopyMessages**已成功复制或移动每封邮件。  <br/> |S_OK  <br/> |
|**IMAPIFolder:: CopyMessages**无法成功复制或移动每封邮件。  <br/> |MAPI_W_PARTIAL_COMPLETION  <br/> |
|**IMAPIFolder:: CopyMessages**无法完成。  <br/> |任何错误值  <br/> |
   
当**IMAPIFolder:: CopyMessages**无法完成时, 请不要假定没有执行任何操作。 **IMAPIFolder:: CopyMessages**可能在遇到此错误之前能够复制或移动一个或多个邮件。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)

