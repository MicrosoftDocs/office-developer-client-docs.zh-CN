---
title: 使用多个 Exchange 帐户
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
# <a name="using-multiple-exchange-accounts"></a>使用多个 Exchange 帐户

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
microsoft outlook 2010 和 microsoft outlook 2013 支持与多个 exchange 电子邮件帐户的集成。 在 outlook 2010 或 outlook 2013 中, 用户可以将两个 exchange 帐户添加到同一个配置文件, 并且仍能享受丰富的 exchange 功能, 如发布的全局地址列表 (GAL)、exchange 外部配置和文件夹共享。
  
熟悉 Microsoft Office Outlook 2007 和更早版本的 MAPI 配置文件部分的人会知道, exchange 设置 (如电子邮件用户名和服务器名称) 存储在 "固定 exchange 全局配置文件" 部分中的 " **pbGlobalProfileSectionGuid**" 中。 在 outlook 2010 和 outlook 2013 中, 每个 Exchange 帐户都需要自己的配置文件部分来存储设置, 使**pbGlobalProfileSectionGuid**过时。 
  
outlook 2010 和 outlook 2013 Exchange 设置仍存储在配置文件中, 但包含其设置的配置文件部分的唯一标识符是按配置文件动态分配的。 配置文件中的 Exchange 设置的位置存储在[PidTagExchangeProfileSectionId 规范属性](pidtagexchangeprofilesectionid-canonical-property.md)中, 可以在 Exchange 帐户的 "邮件服务配置文件" 部分找到该属性。 此外, 还可以在此帐户的邮件服务中的每个提供程序的 "配置文件" 部分中找到此属性。 唯一标识符不存储在服务器上, 并且在配置文件中将有所不同。
  
outlook 2010 和 outlook 2013 将**PidTagExchangeProfileSectionId**用作指定 Exchange 帐户的唯一标识符。 以这种方式使用时, 此唯一标识符称为 " **emsmdbUID**"。 对于某些 MAPI 和 Outlook 操作, 可能需要**emsmdbUID**来指定应将哪个 Exchange 帐户用于此操作。 
  
为了支持多个 Exchange 帐户, 您必须对代码中的新函数进行一些调用。 将使用**entryID**的任何呼叫和[IAddrBook:: OpenEntry](iaddrbook-openentry.md)或[IAddrBook:: CompareEntryIDs](iaddrbook-compareentryids.md)在[IMailUser: IMAPIProp](imailuserimapiprop.md)和[IDistList: IMAPIContainer](idistlistimapicontainer.md)上替换为以下函数之一。 
  
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

仍支持在创建此新的**emsmdbUID**部分之前写入的任何 MAPI 客户端。 这些客户端将继续检索上一个全局部分**pbGlobalProfileSectionGuid**。 此配置文件部分的查询将被重定向到一个用于处理旧查询的指定 Exchange 帐户。 通过查看邮件服务表并添加 PR_EMSMDB_LEGACY 的列, 可以确定用于处理旧调用的帐户。 只有一项邮件服务将此设置为 true, 并且其**PidTagExchangeProfileSectionId**称为旧版**emsmdbUID**。
  
> [!NOTE]
> 可配置的 MAPI 设置 (如默认存储和默认帐户) 对哪个帐户处理旧呼叫没有影响。 无法配置处理旧呼叫的帐户。 
  
将旧版帐户的**emsmdbUID**复制到 Outlook 全局配置文件部分。 如果此属性不存在, 则查询邮件服务表将确定是什么帐户是旧处理程序, 并在 Outlook 全局配置文件部分中设置值。 
  
若要清楚, outlook 全局配置文件部分与 "exchange 全局配置文件" 部分不同, 在 outlook 2010 和 outlook 2013 中, exchange 全局配置文件部分不再是真正的全局, 因为您可以拥有多个 Exchange 帐户。 outlook "全局配置文件" 部分包含有关 Outlook 的属性, 例如文件夹的状态 MRU 或全局连接的状态。
  
## <a name="address-book-account-contexts"></a>通讯簿帐户上下文

若要使用多个 Exchange 帐户正确解析地址, 请使用采用帐户上下文的新函数, 以便对通讯簿的呼叫可以搜索正确的 Exchange 帐户。
  
由于没有完全支持多个 Exchange 的 api, 一些以前的通讯簿 api 已被弃用。 此帐户上下文通常为**emsmdbUID**。
  
除了**emsmdbUID**之外, 多个 Exchange 帐户也有一个**emsabpUID**。
  
1. **emsmdbUID**值标识帐户上下文。 
    
2. **emsabpUID**值标识一个 Exchange 通讯簿提供程序。 
    
在解析收件人时, 通常使用**emsabpUID**值。 使用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)解析收件人时, Exchange 收件人行包含**PR_AB_PROVIDERS** (0x3D010102) 属性, 其中包含**emsabpUID**值。 此**emsabpUID**值标识特定收件人的 Exchange 通讯簿提供程序。 
  
如果要确定特定**emsmdbUID**的**emsabpUID**值, 请打开**emsmdbUID**的 "配置文件" 部分并获取**PR_EMSABP_USER_UID** (0x0x3D1A0102) 属性。 
  
如果要调用[IAddrBook::P reparerecips](iaddrbook-preparerecips.md), 请确保您传入的列表中的 Exchange 收件人包含的**PR_AB_PROVIDERS**属性包含与通讯簿提供程序相对应的**emsabpUID** 。收件人属于。 调用[IAddrBook:](iaddrbook-preparerecips.md)从[IAddrBook:: ResolveName](iaddrbook-resolvename.md)获取的行上:P reparerecips 不需要其他任何操作, 但某些代码将对仅包含**IAddrBook**的行调用[reparerecips::P PR_ENTRYID](iaddrbook-preparerecips.md)财产. 此情况和类似情况中的行都应包含**PR_ENTRYID**和**PR_AB_PROVIDERS** , 并且**PR_AB_PROVIDERS**属性设置为正确的**emsabpUID**。
  
解析多个 Exchange 帐户的过程的简单说明如下:
  
- 如果给定了服务唯一标识符, 您的代码将在**PR_SERVICE_UID**属性的邮件存储区中查找与您拥有的项匹配的表。 在这里, 您可以确定正确的**PR_MDB_PROVIDER**。 此行包含适当的存储区。
    
- 在给定**emsmdbUID**的情况下, 您的代码会在邮件服务表中查找公开与**emsmdbUID**匹配的**PidTagExchangeProfileSectionId**的行。
    
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


[如何打开 "全局配置文件" 部分](https://support.microsoft.com/kb/188482)

