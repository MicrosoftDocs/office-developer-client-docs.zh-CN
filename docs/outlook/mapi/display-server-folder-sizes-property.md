---
title: 显示服务器文件夹大小属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- Display Server Folder Sizes Property
api_type:
- COM
ms.assetid: 38429fdb-be93-213a-a780-80f9837f55fa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1ddf4501918d598169a3a74fd1c8d2ac38499cd2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774798"
---
# <a name="display-server-folder-sizes-property"></a>显示服务器文件夹大小属性

  
  
**适用于**： Outlook 
  
显示 Outlook**文件夹大小**对话框中的服务器上的指定文件夹的大小。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|公开上：  <br/> |[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象  <br/> |
|通过创建：  <br/> |存储提供程序  <br/> |
|通过来访问：  <br/> |Outlook 和其他客户端  <br/> |
|属性类型  <br/> |PT_BOOLEAN  <br/> |
|访问类型：  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

若要提供的任何存储功能，存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。 当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。 [HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。 
  
若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。 调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PS_PUBLIC_STRINGS  <br/> |
|ulKind:  <br/> |MNID_STRING  <br/> |
|Kind.lpwstrName:  <br/> |L"urn： 架构-microsoft-com:office:outlook #serverfoldersizes"  <br/> |
   
在 Microsoft Outlook 2003 Service Pack (SP) 1年支持此属性。 如果 Outlook 版本早于 Outlook 2003 SP 1，或其值为**false**，则 Outlook 将上本地存储中显示文件夹的大小。 如果此属性设置在使用 Outlook 2003 SP 1 的存储区上，Outlook 将查询服务器和本地驱动器上的每个指定文件夹的大小。 
  
查询服务器上的文件夹大小，Outlook 会打开存储上的文件夹与[IMsgStore::OpenEntry](imsgstore-openentry.md)，传递标志**MAPI_NO_CACHE**，，然后它查询的**PR_MESSAGE_SIZE_EXTENDED**。 存储提供程序然后返回服务器上的文件夹大小。
  
要查询的本地驱动器上的文件夹的大小，Outlook 将打开如果没有**MAPI_NO_CACHE**标志文件夹。 然后它**PR_MESSAGE_SIZE_EXTENDED**; 查询存储提供程序应在本地驱动器返回指定的文件夹的大小。
  
设置此属性，将同步到服务器的存储内容的存储提供程序可以显示 Outlook**文件夹大小**对话框中的服务器上的文件夹大小数据。 用户可以进行比较，与服务器配额其当前服务器存储使用情况。 
  

