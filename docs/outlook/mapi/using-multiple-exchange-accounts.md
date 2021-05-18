---
title: 使用多个Exchange帐户
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4e1804bf-4c50-4942-a7ab-9a8caf1be7e5
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: a5792ebaf78d77924bc3157be63d937b66e9f4b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329650"
---
# <a name="using-multiple-exchange-accounts"></a>使用多个Exchange帐户

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持与多个 Exchange 电子邮件帐户集成。 在 Outlook 2010 或 Outlook 2013 中，用户可以向同一配置文件添加两个 exchange 帐户，并仍享受丰富的 Exchange 功能，如发布的全局地址列表 (GAL) 、Exchange Out-of-Office 配置和文件夹共享。
  
熟悉 Microsoft Office Outlook 2007 及更早版本 MAPI 配置文件部分的用户知道，Exchange 设置（如电子邮件用户名和服务器名称）存储在固定的 Exchange 全局配置文件部分 **pbGlobalProfileSectionGuid** 中。 在 Outlook 2010 和 Outlook 2013 中，每个 Exchange 帐户都需要自己的配置文件部分来存储设置，使得 **pbGlobalProfileSectionGuid** 已过时。 
  
Outlook 2010 和 Outlook 2013 Exchange 设置仍存储在配置文件中，但包含其设置的配置文件节的唯一标识符是按配置文件动态分配的。 配置文件中 Exchange 设置的位置存储在[PidTagExchangeProfileSectionId](pidtagexchangeprofilesectionid-canonical-property.md)规范属性中，可在 Exchange 帐户的邮件服务配置文件部分找到该属性。 此属性还可以在帐户的此邮件服务中每个提供程序的配置文件部分找到。 唯一标识符不存储在服务器上，并且跨配置文件将不同。
  
Outlook 2010 Outlook 2013 使用 **PidTagExchangeProfileSectionId** 作为唯一标识符来指定 Exchange 帐户。 当通过此方式使用时，此唯一标识符称为 **emsmdbUID**。 对于一些 MAPI Outlook操作，可能需要 **emsmdbUID** 来指定操作Exchange帐户。 
  
为了支持多个Exchange帐户，必须在代码中对新函数进行一些调用。 将 IMailUser 上使用 **entryID** 和 [IAddrBook：：OpenEntry](iaddrbook-openentry.md)或 [IAddrBook：：CompareEntryIDs](iaddrbook-compareentryids.md)的任何调用替换为以下函数之一 [： IMAPIProp](imailuserimapiprop.md)和 [IDistList ： IMAPIContainer。](idistlistimapicontainer.md) 
  
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
    
## <a name="legacy-support"></a>旧版支持

在新建 **emsmdbUID** 节之前编写的任何 MAPI 客户端仍受支持。 这些客户端将继续检索上一个全局部分 **pbGlobalProfileSectionGuid**。 此配置文件节的查询将重定向到一个Exchange查询的帐户。 通过查看邮件服务表并添加用于处理旧呼叫的列，可以确定处理旧呼叫PR_EMSMDB_LEGACY。 只有一个邮件服务将此设置为 true，其 **PidTagExchangeProfileSectionId** 称为旧 **emsmdbUID**。
  
> [!NOTE]
> 可配置的 MAPI 设置（如默认存储和默认帐户）对哪个帐户处理旧版呼叫没有影响。 无法配置处理旧版呼叫的帐户。 
  
旧 **帐户的 emsmdbUID** 将复制到全局配置文件Outlook中。 如果此属性不存在，则查询邮件服务表将确定哪个帐户是旧处理程序，并设置"全局配置文件"Outlook的值。 
  
很明显，Outlook Global Profile Section 不同于 Exchange Global Profile Section，在 Outlook 2010 和 Outlook 2013 中，Exchange Global Profile Section 不再真正全局，因为您可以有多个 Exchange 帐户。 "Outlook配置文件"部分包含有关Outlook的属性，如文件夹 MRU 的状态或全局连接的状态。
  
## <a name="address-book-account-contexts"></a>通讯簿帐户上下文

若要正确解析多个 Exchange 帐户的地址，请使用采用帐户上下文的新函数，以便对通讯簿的调用搜索正确的 Exchange 帐户。
  
以前的一些通讯簿 API 已弃用，因为 API 并非完全具有多个Exchange功能。 此帐户上下文通常为 **emsmdbUID**。
  
除了 **emsmdbUID** 之外，多个Exchange还具有 **emsabpUID**。
  
1. **emsmdbUID** 值标识帐户上下文。 
    
2. **emsabpUID** 值标识Exchange提供程序。 
    
在解析收件人时，通常使用 **emsabpUID** 值。 使用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md)解析收件人时，Exchange行包含 **PR_AB_PROVIDERS** (0x3D010102) 属性，其中包含 **emsabpUID** 值。 此 **emsabpUID** 值标识Exchange收件人的通讯簿提供程序。 
  
如果要确定特定 **emsmdbUID** 的 **emsabpUID** 值，请打开 **emsmdbUID** 的配置文件部分，并获取 **PR_EMSABP_USER_UID** (0x0x3D1A0102) 属性。 
  
如果要调用 [IAddrBook：:P repareRecips，](iaddrbook-preparerecips.md)请确保所传递列表中的 Exchange 收件人包含与收件人所属的通讯簿提供程序对应的 **emsabpUID** 的 **PR_AB_PROVIDERS** 属性。 对从 [IAddrBook：：ResolveName](iaddrbook-resolvename.md)获取的行调用 [IAddrBook：:P repareRecips](iaddrbook-preparerecips.md)无需任何其他操作，但某些代码将在仅包含 **PR_ENTRYID** 属性的行上调用 [IAddrBook：:P repareRecips。](iaddrbook-preparerecips.md) 此情况及类似情况下的行 **应包含** PR_ENTRYID 和 **PR_AB_PROVIDERS，PR_AB_PROVIDERS****属性设置为** 正确的 **emsabpUID**。
  
解析多个帐户的过程的简单Exchange如下：
  
- 在给定服务唯一标识符后，代码将查找与拥有的属性匹配的 **PR_SERVICE_UID** 属性的邮件存储表。 你可以从该位置确定 **正确的PR_MDB_PROVIDER。** 此行包含相应的存储区。
    
- 在 **给定 emsmdbUID** 后，您的代码在邮件服务表中查找公开与 **emsmdbUID** 匹配的 **PidTagExchangeProfileSectionId** 的行。
    
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


[如何打开"全局配置文件"部分](https://support.microsoft.com/kb/188482)

