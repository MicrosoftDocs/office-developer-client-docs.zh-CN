---
title: IMAPISupport IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport
api_type:
- COM
ms.assetid: 92bfe604-18dd-46a1-9ae8-0b04167606bd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6da488408d3be9464d6ae1e016d5095707d451e4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415437"
---
# <a name="imapisupport--iunknown"></a>IMAPISupport : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为通常由服务提供程序和邮件服务入口点功能执行的任务提供实现。 当 MAPI 调用其提供程序对象的登录方法时，服务提供商会收到指向其支持对象的指针。 邮件服务在调用其入口点函数时接收其支持对象指针。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi.h  <br/> |
|公开者：  <br/> |支持对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
|接口标识符：  <br/> |IID_IMAPISup  <br/> |
|指针类型：  <br/> |LPMAPISUP  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](imapisupport-getlasterror.md) <br/> |返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个支持对象错误的信息。  <br/> |
|[GetMemAllocRoutines](imapisupport-getmemallocroutines.md) <br/> |检索 MAPI 内存分配和处理函数的地址 ([MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)) 。 [](mapiallocatemore.md)  <br/> |
|[Subscribe](imapisupport-subscribe.md) <br/> |注册通知接收器以通过 MAPI 接收通知。  <br/> |
|[取消订阅](imapisupport-unsubscribe.md) <br/> |取消发送之前通过调用 Subscribe 方法建立 **的通知** 的责任。  <br/> |
|[Notify](imapisupport-notify.md) <br/> |将指定事件的通知发送到最初通过 **Subscribe** 方法为通知注册的通知源。  <br/> |
|[ModifyStatusRow](imapisupport-modifystatusrow.md) <br/> |通过添加新行或修改现有行来修改状态表。  <br/> |
|[OpenProfileSection](imapisupport-openprofilesection.md) <br/> |打开当前配置文件的一部分并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问  <br/> |
|[RegisterPreprocessor](imapisupport-registerpreprocessor.md) <br/> |在符合 [PreprocessMessage](preprocessmessage.md) 原型模型 (注册传输提供程序的预处理器) 。  <br/> |
|[NewUID](imapisupport-newuid.md) <br/> |创建要用作唯一标识符的新 [MAPIUID](mapiuid.md) 结构。  <br/> |
|[MakeInvalid](imapisupport-makeinvalid.md) <br/> |将对象标记为不可用。  <br/> |
|[SpoolerYield](imapisupport-spooleryield.md) <br/> |将 CPU 控制权授予 MAPI 后台处理程序，以便它可以执行认为必要的任何任务。  <br/> |
|[SpoolerNotify](imapisupport-spoolernotify.md) <br/> |通知 MAPI 后台处理程序状态更改或服务请求。  <br/> |
|[CreateOneOff](imapisupport-createoneoff.md) <br/> |为一次地址创建条目标识符。  <br/> |
|[SetProviderUID](imapisupport-setprovideruid.md) <br/> |注册一个唯一表示服务提供商的 **MAPIUID** 结构。  <br/> |
|[CompareEntryIDs](imapisupport-compareentryids.md) <br/> |比较两个条目标识符以确定它们是否引用同一个对象。  <br/> |
|[OpenTemplateID](imapisupport-opentemplateid.md) <br/> |在外通讯簿提供程序中打开收件人条目。  <br/> |
|[OpenEntry](imapisupport-openentry.md) <br/> |打开对象并返回接口指针以进一步访问。  <br/> |
|[GetOneOffTable](imapisupport-getoneofftable.md) <br/> |返回一个指向 MAPI 一 (表的指针，该表包含所有通讯簿提供程序都支持创建新收件人的) 。  <br/> |
|[Address](imapisupport-address.md) <br/> |显示公用地址对话框。  <br/> |
|[详细信息](imapisupport-details.md) <br/> |显示一个对话框，其中显示有关特定通讯簿条目的详细信息。  <br/> |
|[NewEntry](imapisupport-newentry.md) <br/> |将新收件人直接添加到通讯簿容器或传出邮件的收件人列表。  <br/> |
|[DoConfigPropsheet](imapisupport-doconfigpropsheet.md) <br/> |显示配置属性表。  <br/> |
|[CopyMessages](imapisupport-copymessages.md) <br/> |将邮件从一个文件夹复制或移动到另一个文件夹。  <br/> |
|[CopyFolder](imapisupport-copyfolder.md) <br/> |将文件夹从当前父文件夹复制或移动到另一个父文件夹。  <br/> |
|[DoCopyTo](imapisupport-docopyto.md) <br/> |将一个对象的所有属性（专门排除的属性除外）复制或移动到另一个对象。  <br/> |
|[DoCopyProps](imapisupport-docopyprops.md) <br/> |将对象的一个或多个属性复制或移动到另一个对象。  <br/> |
|[DoProgressDialog](imapisupport-doprogressdialog.md) <br/> |检索显示进度指示器的进度对象。  <br/> |
|[ReadReceipt](imapisupport-readreceipt.md) <br/> |生成邮件的已读或非读报告。  <br/> |
|[PrepareSubmit](imapisupport-preparesubmit.md) <br/> |准备消息以提交到 MAPI 后台处理程序。  <br/> |
|[ExpandRecips](imapisupport-expandrecips.md) <br/> |完成邮件的收件人列表，扩展特定通讯组列表。  <br/> |
|[DoSentMail](imapisupport-dosentmail.md) <br/> |处理已发送的邮件。  <br/> |
|[OpenAddressBook](imapisupport-openaddressbook.md) <br/> |提供对通讯簿的访问。  <br/> |
|[CompleteMsg](imapisupport-completemsg.md) <br/> |对邮件执行后置处理。  <br/> |
|[StoreLogoffTransports](imapisupport-storelogofftransports.md) <br/> |请求有序释放邮件存储。  <br/> |
|[StatusRecips](imapisupport-statusrecips.md) <br/> |生成送达和未送达报告。  <br/> |
|[WrapStoreEntryID](imapisupport-wrapstoreentryid.md) <br/> |将邮件存储的内部条目标识符转换为 MAPI 标准格式的条目标识符。  <br/> |
|[ModifyProfile](imapisupport-modifyprofile.md) <br/> |永久更改邮件存储配置文件部分。  <br/> |
|[IStorageFromStream](imapisupport-istoragefromstream.md) <br/> |实现存储对象以访问流。  <br/> |
|[GetSvcConfigSupportObj](imapisupport-getsvcconfigsupportobj.md) <br/> |创建邮件服务支持对象。  <br/> |
   
## <a name="remarks"></a>备注

通讯簿、邮件存储、传输提供程序和邮件服务各自有其自己的支持对象。 服务提供程序和消息服务会调用其支持对象中的方法，作为实现其他接口方法的一部分。 每个不同的支持对象都有应用于其调用方的方法的完整实现;不适用的方法返回MAPI_E_NO_SUPPORT。 通讯簿提供程序支持对象具有以下方法的实现：
  
||||
|:-----|:-----|:-----|
|**Address** <br/> |**CompareEntryIDs** <br/> |**CreateOneOff** <br/> |
|**详细信息** <br/> |**DoConfigPropsheet** <br/> |**DoProgressDialog** <br/> |
|**GetLastError** <br/> |**GetMemAllocRoutines** <br/> |**GetOneOffTable** <br/> |
|**IStorageFromStream** <br/> |**GetSvcConfigSupportObj** <br/> |**MakeInvalid** <br/> |
|**ModifyStatusRow** <br/> |**NewEntry** <br/> |**NewUID** <br/> |
|**Notify** <br/> |**OpenAddressBook** <br/> |**OpenEntry** <br/> |
|**OpenProfileSection** <br/> |**OpenTemplateID** <br/> |**SetProviderUID** <br/> |
|**Subscribe** <br/> |**取消订阅** <br/> |**WrapStoreEntryID** <br/> |
   
邮件存储提供程序支持对象具有以下方法的实现：
  
||||
|:-----|:-----|:-----|
|**CompareEntryIDs** <br/> |**CompleteMsg** <br/> |**CopyFolder** <br/> |
|**CopyMessages** <br/> |**CreateOneOff** <br/> |**DoCopyProps** <br/> |
|**DoCopyTo** <br/> |**DoConfigPropsheet** <br/> |**DoProgressDialog** <br/> |
|**DoSentMail** <br/> |**ExpandRecips** <br/> |**GetLastError** <br/> |
|**GetMemAllocRoutines** <br/> |**GetSvcConfigSupportObj** <br/> |**MakeInvalid** <br/> |
|**IStorageFromStream** <br/> |**ModifyProfile** <br/> |**ModifyStatusRow** <br/> |
|**NewUID** <br/> |**Notify** <br/> |**OpenAddressBook** <br/> |
|**OpenEntry** <br/> |**OpenProfileSection** <br/> |**PrepareSubmit** <br/> |
|**ReadReceipt** <br/> |**SetProviderUID** <br/> |**SpoolerNotify** <br/> |
|**StoreLogoffTransports** <br/> |**Subscribe** <br/> |**取消订阅** <br/> |
|**WrapStoreEntryID** <br/> |
   
传输提供程序支持对象具有以下方法的实现：
  
||||
|:-----|:-----|:-----|
|**DoConfigPropsheet** <br/> |**CompareEntryIDs** <br/> |**CreateOneOff** <br/> |
|**GetMemAllocRoutines** <br/> |**GetSvcConfigSupportObj** <br/> |**GetLastError** <br/> |
|**IStorageFromStream** <br/> |**MakeInvalid** <br/> |**ModifyStatusRow** <br/> |
|**OpenAddressBook** <br/> |**RegisterPreprocessor** <br/> |**NewUID** <br/> |
|**Notify** <br/> |**OpenProfileSection** <br/> |**OpenEntry** <br/> |
|**StatusRecips** <br/> |**SpoolerNotify** <br/> |**SpoolerYield** <br/> |
|**WrapStoreEntryID** <br/> |**Subscribe** <br/> |**取消订阅** <br/> |
   
邮件服务支持对象具有以下方法的实现：
  
|||
|:-----|:-----|
|**DoConfigPropsheet** <br/> |**GetLastError** <br/> |
|**GetMemAllocRoutines** <br/> |**GetSvcConfigSupportObj** <br/> |
|**MakeInvalid** <br/> |**NewUID** <br/> |
|**OpenProfileSection** <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

