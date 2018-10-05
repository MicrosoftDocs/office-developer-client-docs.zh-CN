---
title: 使用多个 Exchange 帐户
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4e1804bf-4c50-4942-a7ab-9a8caf1be7e5
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 3c0392cd6a885900c1a305cd1cd816a5925745a7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398589"
---
# <a name="using-multiple-exchange-accounts"></a>使用多个 Exchange 帐户

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持多个 exchange 电子邮件帐户与集成。 在 Outlook 2010 或 Outlook 2013 中，用户无法将两个 exchange 帐户添加到的同一配置文件和仍享受丰富的 Exchange 功能，如已发布的全局地址列表 (GAL)、 Exchange 出的 Office 配置和文件夹共享。
  
这些熟悉 Microsoft Office Outlook 2007 MAPI 配置文件部分和早期版本知道，在固定 Exchange 全局配置文件部分**pbGlobalProfileSectionGuid**存储 Exchange 设置，如电子邮件用户的名称和服务器名称。 有关 Exchange 全局配置文件的详细信息，请参阅[如何打开全局配置文件部分](https://support.microsoft.com/kb/188482)。 在 Outlook 2010 和 Outlook 2013 中，每个 Exchange 帐户需要其自己的配置文件一节来存储设置，使**pbGlobalProfileSectionGuid**已过时。 
  
Outlook 2010 和 Outlook 2013 Exchange 设置仍存储在配置文件，但包含其设置的配置文件内容的唯一标识符动态分配每个配置文件。 配置文件中的 Exchange 设置的位置存储在[PidTagExchangeProfileSectionId 规范属性](pidtagexchangeprofilesectionid-canonical-property.md)，可以在 Exchange 帐户的邮件服务配置文件部分中找到。 此属性也找不在配置文件部分中的帐户的此消息服务的每个提供程序。 唯一标识符不存储在服务器上，将配置文件跨不同。
  
Outlook 2010 和 Outlook 2013 使用**PidTagExchangeProfileSectionId**作为唯一标识符指定 Exchange 帐户。 在这种方式使用时，此唯一标识符称为**emsmdbUID**。 对于某些 MAPI 和 Outlook 的操作， **emsmdbUID**可能需要指定的 Exchange 帐户应使用此操作。 
  
为了支持多个 Exchange 帐户，您必须在代码中使用一些新函数的调用。 使用**entryID**和[IAddrBook::OpenEntry](iaddrbook-openentry.md)或[IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md)任何调用替换[IMailUser: IMAPIProp](imailuserimapiprop.md)和[IDistList: IMAPIContainer](idistlistimapicontainer.md)具有以下函数之一。 
  
- [HrCompareABEntryIDsWithExchangeContext](hrcompareabentryidswithexchangecontext.md)
    
- [HrDoABDetailsWithExchangeContext](hrdoabdetailswithexchangecontext.md)
    
- [HrDoABDetailsWithProviderUID](hrdoabdetailswithprovideruid.md)
    
- [HrGetGALFromEmsmdbUID](hrgetgalfromemsmdbuid.md)
    
- [HrOpenABEntryUsingDefaultContext](hropenabentryusingdefaultcontext.md)
    
- [HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md)
    
- [HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md)
    
- [HrOpenABEntryWithProviderUIDSupport](hropenabentrywithprovideruidsupport.md)
    
- [HrOpenABEntryWithResolvedRow](hropenabentrywithresolvedrow.md)
    
- [HrOpenABEntryWithSupport](hropenabentrywithsupport.md)
    
## <a name="legacy-support"></a>旧的支持

仍然支持之前创建的此新**emsmdbUID**部分写入任何 MAPI 客户端。 这些客户端将继续检索以前全局节**pbGlobalProfileSectionGuid**。 此配置文件部分的查询将重定向到一个处理旧的查询的指定 Exchange 帐户。 可以通过查看邮件服务表并将列添加的 PR_EMSMDB_LEGACY 确定处理旧的呼叫的帐户。 只有一个邮件服务可以设置为 true，则和其**PidTagExchangeProfileSectionId**这称为旧版**emsmdbUID**。
  
> [!NOTE]
> 可配置的 MAPI 设置，如默认存储和默认帐户具有帐户在其处理旧的呼叫没有影响。 处理旧式呼叫的帐户不能配置。 
  
旧式帐户**emsmdbUID**复制到 Outlook 全局配置文件部分。 如果该属性不存在，消息服务表中的查询将确定哪个帐户是旧的处理程序，并将值设置的 Outlook 全局配置文件部分。 
  
若要清除，Outlook 全局配置文件部分不同从 Exchange 全局配置文件部分中，并且在 Outlook 2010 和 Outlook 2013 中 Exchange 全局配置文件部分不再真正全局因为可以有多个 Exchange 帐户。 Outlook 全局配置文件部分包含有关 Outlook，如文件夹 MRU 的状态或全局连接状态的属性。
  
## <a name="address-book-account-contexts"></a>通讯簿帐户上下文

若要解决正确使用多个 Exchange 帐户的地址，请使用拍摄帐户上下文，以便调用通讯簿搜索正确的 Exchange 帐户的新功能。
  
因为 Api 未能够完全多个 Exchange 否决的 Api 某些以前通讯簿。 此帐户上下文通常是**emsmdbUID**。
  
除了**emsmdbUID**，多个 Exchange 帐户还有**emsabpUID**。
  
1. **EmsmdbUID**值标识的帐户上下文。 
    
2. **EmsabpUID**值标识 Exchange 通讯簿提供程序。 
    
解析收件人时通常使用**emsabpUID**值。 解析收件人使用[IAddrBook::ResolveName](iaddrbook-resolvename.md)时, Exchange 收件人行包含**PR_AB_PROVIDERS** (0x3D010102) 属性，其中包含**emsabpUID**值。 此**emsabpUID**值标识 Exchange 通讯簿提供程序特定的收件人。 
  
如果您想要确定特定**emsmdbUID** **emsabpUID**值，打开配置文件部分的**emsmdbUID**并获取**PR_EMSABP_USER_UID** (0x0x3D1A0102) 属性。 
  
如果您正在呼叫[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)，请确保您传入的列表中的 Exchange 收件人包含具有**emsabpUID**对应于通讯簿提供程序的**PR_AB_PROVIDERS**属性的收件人所属。 对从[IAddrBook::ResolveName](iaddrbook-resolvename.md)获得的行调用[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)不需要其他操作，但某些代码将在包含仅**PR_ENTRYID**的行上调用[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)属性。 在此行，并且类似的情况下应包含**PR_ENTRYID**和**PR_AB_PROVIDERS** **PR_AB_PROVIDERS**属性设置为正确**emsabpUID**。
  
简单的解析多个 Exchange 帐户的过程说明如下所示：
  
- 给定的服务的唯一标识符， **PR_SERVICE_UID**属性必须一匹配的邮件存储的表中查找您的代码。 从，您可以确定正确的**PR_MDB_PROVIDER**。 此行包含在相应的商店。
    
- 给定**emsmdbUID**，在消息服务表中的行的公开匹配**emsmdbUID** **PidTagExchangeProfileSectionId**中查找您的代码。
    
## <a name="see-also"></a>另请参阅



[HrCompareABEntryIDsWithExchangeContext](hrcompareabentryidswithexchangecontext.md)
  
[HrDoABDetailsWithExchangeContext](hrdoabdetailswithexchangecontext.md)
  
[HrDoABDetailsWithProviderUID](hrdoabdetailswithprovideruid.md)
  
[HrGetGALFromEmsmdbUID](hrgetgalfromemsmdbuid.md)
  
[HrOpenABEntryUsingDefaultContext](hropenabentryusingdefaultcontext.md)
  
[HrOpenABEntryWithExchangeContext](hropenabentrywithexchangecontext.md)
  
[HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md)
  
[HrOpenABEntryWithProviderUIDSupport](hropenabentrywithprovideruidsupport.md)
  
[HrOpenABEntryWithResolvedRow](hropenabentrywithresolvedrow.md)
  
[HrOpenABEntryWithSupport](hropenabentrywithsupport.md)
  
[PidTagExchangeProfileSectionId 规范属性](pidtagexchangeprofilesectionid-canonical-property.md)


[如何打开全局配置文件部分](https://support.microsoft.com/kb/188482)

