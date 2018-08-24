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
ms.openlocfilehash: 4843a52d7441de1e1ab545e80346db8dd308c4bf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590202"
---
# <a name="imapisupport--iunknown"></a>IMAPISupport : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供实现通常由服务提供商和消息服务入口点函数执行的任务。 MAPI 调用其提供商对象的登录方法时，服务提供商收到指向其支持对象的指针。 消息服务对其入口点函数的调用中收到其支持对象指针。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|由公开：  <br/> |支持对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
|接口标识符：  <br/> |IID_IMAPISup  <br/> |
|指针类型：  <br/> |LPMAPISUP  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](imapisupport-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的支持对象错误的信息。  <br/> |
|[GetMemAllocRoutines](imapisupport-getmemallocroutines.md) <br/> |检索 MAPI 内存分配和释放函数 （[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)） 的地址。  <br/> |
|[Subscribe](imapisupport-subscribe.md) <br/> |注册以接收通知通过 MAPI 通知接收器。  <br/> |
|[Unsubscribe](imapisupport-unsubscribe.md) <br/> |取消以前建立与调用**Subscribe**方法发送通知的责任。  <br/> |
|[Notify](imapisupport-notify.md) <br/> |将指定的事件的通知发送到最初通过**Subscribe**方法通知注册的 advise 源。  <br/> |
|[ModifyStatusRow](imapisupport-modifystatusrow.md) <br/> |通过添加新行或修改现有行来修改状态表。  <br/> |
|[OpenProfileSection](imapisupport-openprofilesection.md) <br/> |打开当前配置文件的一部分，并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针  <br/> |
|[RegisterPreprocessor](imapisupport-registerpreprocessor.md) <br/> |注册传输提供程序的预处理器函数 （符合[PreprocessMessage](preprocessmessage.md)原型函数）。  <br/> |
|[NewUID](imapisupport-newuid.md) <br/> |创建一个新的[MAPIUID](mapiuid.md)结构用作唯一标识符。  <br/> |
|[MakeInvalid](imapisupport-makeinvalid.md) <br/> |将对象标记为不可用。  <br/> |
|[SpoolerYield](imapisupport-spooleryield.md) <br/> |到 MAPI 后台处理程序提供的 CPU 的控件，以便它可以执行它认为需要的任何任务。  <br/> |
|[SpoolerNotify](imapisupport-spoolernotify.md) <br/> |通知状态或服务的请求中的更改 MAPI 后台处理程序。  <br/> |
|[CreateOneOff](imapisupport-createoneoff.md) <br/> |创建一个一次性地址的项标识符。  <br/> |
|[SetProviderUID](imapisupport-setprovideruid.md) <br/> |注册**MAPIUID**结构，它唯一表示服务提供商。  <br/> |
|[CompareEntryIDs](imapisupport-compareentryids.md) <br/> |比较两个条目标识符来确定它们是否引用同一个对象。  <br/> |
|[OpenTemplateID](imapisupport-opentemplateid.md) <br/> |在外部地址簿提供程序中打开一个收件人的项。  <br/> |
|[OpenEntry](imapisupport-openentry.md) <br/> |打开一个对象并返回进一步访问的接口指针。  <br/> |
|[GetOneOffTable](imapisupport-getoneofftable.md) <br/> |返回到 MAPI 一次性表格 （所有通讯都簿提供程序支持创建新的收件人的模板的列表） 的指针。  <br/> |
|[地址](imapisupport-address.md) <br/> |显示通用的地址对话框。  <br/> |
|[详细信息](imapisupport-details.md) <br/> |显示一个对话框，显示有关特定通讯簿条目的详细信息。  <br/> |
|[NewEntry](imapisupport-newentry.md) <br/> |直接到通讯簿容器或传出邮件的收件人列表中添加一个新收件人。  <br/> |
|[DoConfigPropsheet](imapisupport-doconfigpropsheet.md) <br/> |显示配置属性表。  <br/> |
|[CopyMessages](imapisupport-copymessages.md) <br/> |复制或移动邮件从一个文件夹到另一个文件夹。  <br/> |
|[CopyFolder](imapisupport-copyfolder.md) <br/> |复制或移动到另一个父文件夹的从其当前的父文件夹的文件夹。  <br/> |
|[DoCopyTo](imapisupport-docopyto.md) <br/> |复制或移动到另一个对象的一个对象，特别是排除的属性，除外的所有属性。  <br/> |
|[DoCopyProps](imapisupport-docopyprops.md) <br/> |复制或移动到另一个对象的一个或多个对象的属性。  <br/> |
|[DoProgressDialog](imapisupport-doprogressdialog.md) <br/> |检索一个进度对象，它显示进度指示器。  <br/> |
|[Readreceipt 已](imapisupport-readreceipt.md) <br/> |生成一个读取或 nonread 的报销单以供一条消息。  <br/> |
|[PrepareSubmit](imapisupport-preparesubmit.md) <br/> |提交到 MAPI 后台处理程序准备一条消息。  <br/> |
|[ExpandRecips](imapisupport-expandrecips.md) <br/> |完成邮件的收件人列表中，展开特定的通讯组列表。  <br/> |
|[DoSentMail](imapisupport-dosentmail.md) <br/> |处理已发送的邮件。  <br/> |
|[OpenAddressBook](imapisupport-openaddressbook.md) <br/> |提供对通讯簿访问。  <br/> |
|[CompleteMsg](imapisupport-completemsg.md) <br/> |执行上一条消息后处理。  <br/> |
|[StoreLogoffTransports](imapisupport-storelogofftransports.md) <br/> |请求的消息存储的有序版本。  <br/> |
|[StatusRecips](imapisupport-statusrecips.md) <br/> |生成送达和原件报告。  <br/> |
|[WrapStoreEntryID](imapisupport-wrapstoreentryid.md) <br/> |转换 MAPI 标准格式中的项标识符的消息存储内部的项标识符。  <br/> |
|[ModifyProfile](imapisupport-modifyprofile.md) <br/> |对做的更改一条消息存储永久的配置文件部分。  <br/> |
|[IStorageFromStream](imapisupport-istoragefromstream.md) <br/> |实现的存储对象访问的流。  <br/> |
|[GetSvcConfigSupportObj](imapisupport-getsvcconfigsupportobj.md) <br/> |创建一个邮件服务支持对象。  <br/> |
   
## <a name="remarks"></a>注解

地址书籍、 消息存储、 传输提供程序和消息每个服务都有其自己的支持对象。 服务提供商和消息服务中的它们的其他接口方法的实现一部分其支持对象调用方法。 每个不同的支持对象已完成实现其呼叫者; 应用于的方法不适用的方法返回 MAPI_E_NO_SUPPORT。 地址簿提供程序支持对象必须实现以下方法：
  
||||
|:-----|:-----|:-----|
|**地址** <br/> |**CompareEntryIDs** <br/> |**CreateOneOff** <br/> |
|**详细信息** <br/> |**DoConfigPropsheet** <br/> |**DoProgressDialog** <br/> |
|**时出错** <br/> |**GetMemAllocRoutines** <br/> |**GetOneOffTable** <br/> |
|**IStorageFromStream** <br/> |**GetSvcConfigSupportObj** <br/> |**MakeInvalid** <br/> |
|**ModifyStatusRow** <br/> |**NewEntry** <br/> |**NewUID** <br/> |
|**Notify** <br/> |**OpenAddressBook** <br/> |**OpenEntry** <br/> |
|**OpenProfileSection** <br/> |**OpenTemplateID** <br/> |**SetProviderUID** <br/> |
|**Subscribe** <br/> |**Unsubscribe** <br/> |**WrapStoreEntryID** <br/> |
   
消息存储提供程序支持对象必须实现以下方法：
  
||||
|:-----|:-----|:-----|
|**CompareEntryIDs** <br/> |**CompleteMsg** <br/> |**CopyFolder** <br/> |
|**CopyMessages** <br/> |**CreateOneOff** <br/> |**DoCopyProps** <br/> |
|**DoCopyTo** <br/> |**DoConfigPropsheet** <br/> |**DoProgressDialog** <br/> |
|**DoSentMail** <br/> |**ExpandRecips** <br/> |**时出错** <br/> |
|**GetMemAllocRoutines** <br/> |**GetSvcConfigSupportObj** <br/> |**MakeInvalid** <br/> |
|**IStorageFromStream** <br/> |**ModifyProfile** <br/> |**ModifyStatusRow** <br/> |
|**NewUID** <br/> |**Notify** <br/> |**OpenAddressBook** <br/> |
|**OpenEntry** <br/> |**OpenProfileSection** <br/> |**PrepareSubmit** <br/> |
|**Readreceipt 已** <br/> |**SetProviderUID** <br/> |**SpoolerNotify** <br/> |
|**StoreLogoffTransports** <br/> |**Subscribe** <br/> |**Unsubscribe** <br/> |
|**WrapStoreEntryID** <br/> |
   
传输提供程序支持的对象必须实现以下方法：
  
||||
|:-----|:-----|:-----|
|**DoConfigPropsheet** <br/> |**CompareEntryIDs** <br/> |**CreateOneOff** <br/> |
|**GetMemAllocRoutines** <br/> |**GetSvcConfigSupportObj** <br/> |**时出错** <br/> |
|**IStorageFromStream** <br/> |**MakeInvalid** <br/> |**ModifyStatusRow** <br/> |
|**OpenAddressBook** <br/> |**RegisterPreprocessor** <br/> |**NewUID** <br/> |
|**Notify** <br/> |**OpenProfileSection** <br/> |**OpenEntry** <br/> |
|**StatusRecips** <br/> |**SpoolerNotify** <br/> |**SpoolerYield** <br/> |
|**WrapStoreEntryID** <br/> |**Subscribe** <br/> |**Unsubscribe** <br/> |
   
消息服务支持对象必须实现以下方法：
  
|||
|:-----|:-----|
|**DoConfigPropsheet** <br/> |**时出错** <br/> |
|**GetMemAllocRoutines** <br/> |**GetSvcConfigSupportObj** <br/> |
|**MakeInvalid** <br/> |**NewUID** <br/> |
|**OpenProfileSection** <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

