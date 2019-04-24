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
# <a name="using-multiple-exchange-accounts"></a><span data-ttu-id="7d176-103">使用多个 Exchange 帐户</span><span class="sxs-lookup"><span data-stu-id="7d176-103">Using Multiple Exchange Accounts</span></span>

  
  
<span data-ttu-id="7d176-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d176-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7d176-105">microsoft outlook 2010 和 microsoft outlook 2013 支持与多个 exchange 电子邮件帐户的集成。</span><span class="sxs-lookup"><span data-stu-id="7d176-105">Microsoft Outlook 2010 and Microsoft Outlook 2013 support integration with multiple exchange email accounts.</span></span> <span data-ttu-id="7d176-106">在 outlook 2010 或 outlook 2013 中, 用户可以将两个 exchange 帐户添加到同一个配置文件, 并且仍能享受丰富的 exchange 功能, 如发布的全局地址列表 (GAL)、exchange 外部配置和文件夹共享。</span><span class="sxs-lookup"><span data-stu-id="7d176-106">In Outlook 2010 or Outlook 2013, a user could add two exchange accounts to the same profile and still enjoy rich Exchange features such as the published global address list (GAL), Exchange Out-of-Office configuration, and folder sharing.</span></span>
  
<span data-ttu-id="7d176-107">熟悉 Microsoft Office Outlook 2007 和更早版本的 MAPI 配置文件部分的人会知道, exchange 设置 (如电子邮件用户名和服务器名称) 存储在 "固定 exchange 全局配置文件" 部分中的 " **pbGlobalProfileSectionGuid**" 中。</span><span class="sxs-lookup"><span data-stu-id="7d176-107">Those familiar with the MAPI profile sections for Microsoft Office Outlook 2007 and earlier know that Exchange settings, such as the email user name and server name, are stored in the fixed Exchange Global Profile section, **pbGlobalProfileSectionGuid**.</span></span> <span data-ttu-id="7d176-108">在 outlook 2010 和 outlook 2013 中, 每个 Exchange 帐户都需要自己的配置文件部分来存储设置, 使**pbGlobalProfileSectionGuid**过时。</span><span class="sxs-lookup"><span data-stu-id="7d176-108">In Outlook 2010 and Outlook 2013, each Exchange account needs its own profile section to store settings, making the **pbGlobalProfileSectionGuid** obsolete.</span></span> 
  
<span data-ttu-id="7d176-109">outlook 2010 和 outlook 2013 Exchange 设置仍存储在配置文件中, 但包含其设置的配置文件部分的唯一标识符是按配置文件动态分配的。</span><span class="sxs-lookup"><span data-stu-id="7d176-109">Outlook 2010 and Outlook 2013 Exchange settings are still stored in the profile, but a unique identifier for the profile section that contains their settings is dynamically allocated per profile.</span></span> <span data-ttu-id="7d176-110">配置文件中的 Exchange 设置的位置存储在[PidTagExchangeProfileSectionId 规范属性](pidtagexchangeprofilesectionid-canonical-property.md)中, 可以在 Exchange 帐户的 "邮件服务配置文件" 部分找到该属性。</span><span class="sxs-lookup"><span data-stu-id="7d176-110">The location of the Exchange settings in the profile is stored in the [PidTagExchangeProfileSectionId Canonical Property](pidtagexchangeprofilesectionid-canonical-property.md), which can be found in the message service profile section of the Exchange account.</span></span> <span data-ttu-id="7d176-111">此外, 还可以在此帐户的邮件服务中的每个提供程序的 "配置文件" 部分中找到此属性。</span><span class="sxs-lookup"><span data-stu-id="7d176-111">This property can also be found in the profile section for each provider in this message service of the account.</span></span> <span data-ttu-id="7d176-112">唯一标识符不存储在服务器上, 并且在配置文件中将有所不同。</span><span class="sxs-lookup"><span data-stu-id="7d176-112">The unique identifier is not stored on the server and will be different across profiles.</span></span>
  
<span data-ttu-id="7d176-113">outlook 2010 和 outlook 2013 将**PidTagExchangeProfileSectionId**用作指定 Exchange 帐户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7d176-113">Outlook 2010 and Outlook 2013 use the **PidTagExchangeProfileSectionId** as a unique identifier to specify an Exchange account.</span></span> <span data-ttu-id="7d176-114">以这种方式使用时, 此唯一标识符称为 " **emsmdbUID**"。</span><span class="sxs-lookup"><span data-stu-id="7d176-114">When used in this manner, this unique identifier is known as the **emsmdbUID**.</span></span> <span data-ttu-id="7d176-115">对于某些 MAPI 和 Outlook 操作, 可能需要**emsmdbUID**来指定应将哪个 Exchange 帐户用于此操作。</span><span class="sxs-lookup"><span data-stu-id="7d176-115">For some MAPI and Outlook operations, an **emsmdbUID** might be required to specify which Exchange account should be used for the operation.</span></span> 
  
<span data-ttu-id="7d176-116">为了支持多个 Exchange 帐户, 您必须对代码中的新函数进行一些调用。</span><span class="sxs-lookup"><span data-stu-id="7d176-116">In order to support multiple Exchange accounts, you must use some calls to new functions in your code.</span></span> <span data-ttu-id="7d176-117">将使用**entryID**的任何呼叫和[IAddrBook:: OpenEntry](iaddrbook-openentry.md)或[IAddrBook:: CompareEntryIDs](iaddrbook-compareentryids.md)在[IMailUser: IMAPIProp](imailuserimapiprop.md)和[IDistList: IMAPIContainer](idistlistimapicontainer.md)上替换为以下函数之一。</span><span class="sxs-lookup"><span data-stu-id="7d176-117">Replace any call that uses an **entryID** and either [IAddrBook::OpenEntry](iaddrbook-openentry.md) or [IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md) on [IMailUser : IMAPIProp](imailuserimapiprop.md) and [IDistList : IMAPIContainer](idistlistimapicontainer.md) with one of the following functions.</span></span> 
  
- [<span data-ttu-id="7d176-118">HrCompareABEntryIDsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="7d176-118">HrCompareABEntryIDsWithExchangeContext</span></span>](hrcompareabentryidswithexchangecontext.md)
    
- [<span data-ttu-id="7d176-119">HrDoABDetailsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="7d176-119">HrDoABDetailsWithExchangeContext</span></span>](hrdoabdetailswithexchangecontext.md)
    
- [<span data-ttu-id="7d176-120">HrDoABDetailsWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="7d176-120">HrDoABDetailsWithProviderUID</span></span>](hrdoabdetailswithprovideruid.md)
    
- [<span data-ttu-id="7d176-121">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="7d176-121">HrGetGALFromEmsmdbUID</span></span>](hrgetgalfromemsmdbuid.md)
    
- [<span data-ttu-id="7d176-122">HrOpenABEntryUsingDefaultContext</span><span class="sxs-lookup"><span data-stu-id="7d176-122">HrOpenABEntryUsingDefaultContext</span></span>](hropenabentryusingdefaultcontext.md)
    
- [<span data-ttu-id="7d176-123">HrOpenABEntryWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="7d176-123">HrOpenABEntryWithExchangeContext</span></span>](hropenabentrywithexchangecontext.md)
    
- [<span data-ttu-id="7d176-124">HrOpenABEntryWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="7d176-124">HrOpenABEntryWithProviderUID</span></span>](hropenabentrywithprovideruid.md)
    
- [<span data-ttu-id="7d176-125">HrOpenABEntryWithProviderUIDSupport</span><span class="sxs-lookup"><span data-stu-id="7d176-125">HrOpenABEntryWithProviderUIDSupport</span></span>](hropenabentrywithprovideruidsupport.md)
    
- [<span data-ttu-id="7d176-126">HrOpenABEntryWithResolvedRow</span><span class="sxs-lookup"><span data-stu-id="7d176-126">HrOpenABEntryWithResolvedRow</span></span>](hropenabentrywithresolvedrow.md)
    
- [<span data-ttu-id="7d176-127">HrOpenABEntryWithSupport</span><span class="sxs-lookup"><span data-stu-id="7d176-127">HrOpenABEntryWithSupport</span></span>](hropenabentrywithsupport.md)
    
## <a name="legacy-support"></a><span data-ttu-id="7d176-128">旧版支持</span><span class="sxs-lookup"><span data-stu-id="7d176-128">Legacy support</span></span>

<span data-ttu-id="7d176-129">仍支持在创建此新的**emsmdbUID**部分之前写入的任何 MAPI 客户端。</span><span class="sxs-lookup"><span data-stu-id="7d176-129">Any MAPI clients written before the creation of this new **emsmdbUID** section are still supported.</span></span> <span data-ttu-id="7d176-130">这些客户端将继续检索上一个全局部分**pbGlobalProfileSectionGuid**。</span><span class="sxs-lookup"><span data-stu-id="7d176-130">These clients will continue to retrieve the previous global section, **pbGlobalProfileSectionGuid**.</span></span> <span data-ttu-id="7d176-131">此配置文件部分的查询将被重定向到一个用于处理旧查询的指定 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="7d176-131">Queries for this profile section will be redirected to one designated Exchange account that handles legacy inquiries.</span></span> <span data-ttu-id="7d176-132">通过查看邮件服务表并添加 PR_EMSMDB_LEGACY 的列, 可以确定用于处理旧调用的帐户。</span><span class="sxs-lookup"><span data-stu-id="7d176-132">The account that handles the legacy calls can be determined by looking at the message service table and adding a column for PR_EMSMDB_LEGACY.</span></span> <span data-ttu-id="7d176-133">只有一项邮件服务将此设置为 true, 并且其**PidTagExchangeProfileSectionId**称为旧版**emsmdbUID**。</span><span class="sxs-lookup"><span data-stu-id="7d176-133">Only one message service will have this set to true, and its **PidTagExchangeProfileSectionId** is called the legacy **emsmdbUID**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7d176-134">可配置的 MAPI 设置 (如默认存储和默认帐户) 对哪个帐户处理旧呼叫没有影响。</span><span class="sxs-lookup"><span data-stu-id="7d176-134">Configurable MAPI settings such as the default store and the default account have no effect on which account handles legacy calls.</span></span> <span data-ttu-id="7d176-135">无法配置处理旧呼叫的帐户。</span><span class="sxs-lookup"><span data-stu-id="7d176-135">The account that handles the legacy calls cannot be configured.</span></span> 
  
<span data-ttu-id="7d176-136">将旧版帐户的**emsmdbUID**复制到 Outlook 全局配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="7d176-136">The **emsmdbUID** of the legacy account is copied to the Outlook Global Profile Section.</span></span> <span data-ttu-id="7d176-137">如果此属性不存在, 则查询邮件服务表将确定是什么帐户是旧处理程序, 并在 Outlook 全局配置文件部分中设置值。</span><span class="sxs-lookup"><span data-stu-id="7d176-137">If this property does not exist, querying for the message services table will determine what account is the legacy handler and set the value in the Outlook Global Profile Section.</span></span> 
  
<span data-ttu-id="7d176-138">若要清楚, outlook 全局配置文件部分与 "exchange 全局配置文件" 部分不同, 在 outlook 2010 和 outlook 2013 中, exchange 全局配置文件部分不再是真正的全局, 因为您可以拥有多个 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="7d176-138">To be clear, the Outlook Global Profile Section differs from the Exchange Global Profile Section, and in Outlook 2010 and Outlook 2013 the Exchange Global Profile Section is no longer really global because you can have multiple Exchange accounts.</span></span> <span data-ttu-id="7d176-139">outlook "全局配置文件" 部分包含有关 Outlook 的属性, 例如文件夹的状态 MRU 或全局连接的状态。</span><span class="sxs-lookup"><span data-stu-id="7d176-139">The Outlook Global Profile section contains properties about Outlook, such as the state of the folder MRU or the state of the global connection.</span></span>
  
## <a name="address-book-account-contexts"></a><span data-ttu-id="7d176-140">通讯簿帐户上下文</span><span class="sxs-lookup"><span data-stu-id="7d176-140">Address Book Account Contexts</span></span>

<span data-ttu-id="7d176-141">若要使用多个 Exchange 帐户正确解析地址, 请使用采用帐户上下文的新函数, 以便对通讯簿的呼叫可以搜索正确的 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="7d176-141">To resolve addresses correctly with multiple Exchange accounts, use the new functions that take an account context so that calls to the address book search the correct Exchange account.</span></span>
  
<span data-ttu-id="7d176-142">由于没有完全支持多个 Exchange 的 api, 一些以前的通讯簿 api 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="7d176-142">Some previous address book APIs were deprecated because the APIs were not fully multiple Exchange capable.</span></span> <span data-ttu-id="7d176-143">此帐户上下文通常为**emsmdbUID**。</span><span class="sxs-lookup"><span data-stu-id="7d176-143">This account context is usually an **emsmdbUID**.</span></span>
  
<span data-ttu-id="7d176-144">除了**emsmdbUID**之外, 多个 Exchange 帐户也有一个**emsabpUID**。</span><span class="sxs-lookup"><span data-stu-id="7d176-144">In addition to the **emsmdbUID**, multiple Exchange accounts also have an **emsabpUID**.</span></span>
  
1. <span data-ttu-id="7d176-145">**emsmdbUID**值标识帐户上下文。</span><span class="sxs-lookup"><span data-stu-id="7d176-145">The **emsmdbUID** value identifies the account context.</span></span> 
    
2. <span data-ttu-id="7d176-146">**emsabpUID**值标识一个 Exchange 通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="7d176-146">The **emsabpUID** value identifies an Exchange address book provider.</span></span> 
    
<span data-ttu-id="7d176-147">在解析收件人时, 通常使用**emsabpUID**值。</span><span class="sxs-lookup"><span data-stu-id="7d176-147">The **emsabpUID** value is typically used when resolving a recipient.</span></span> <span data-ttu-id="7d176-148">使用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)解析收件人时, Exchange 收件人行包含**PR_AB_PROVIDERS** (0x3D010102) 属性, 其中包含**emsabpUID**值。</span><span class="sxs-lookup"><span data-stu-id="7d176-148">When resolving a recipient using [IAddrBook::ResolveName](iaddrbook-resolvename.md), an Exchange recipient row contains the **PR_AB_PROVIDERS** (0x3D010102) property, which contains the **emsabpUID** value.</span></span> <span data-ttu-id="7d176-149">此**emsabpUID**值标识特定收件人的 Exchange 通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="7d176-149">This **emsabpUID** value identifies the Exchange address book provider for the specific recipient.</span></span> 
  
<span data-ttu-id="7d176-150">如果要确定特定**emsmdbUID**的**emsabpUID**值, 请打开**emsmdbUID**的 "配置文件" 部分并获取**PR_EMSABP_USER_UID** (0x0x3D1A0102) 属性。</span><span class="sxs-lookup"><span data-stu-id="7d176-150">If you want to determine the **emsabpUID** value for a particular **emsmdbUID**, open up the profile section for the **emsmdbUID** and get the **PR_EMSABP_USER_UID** (0x0x3D1A0102) property.</span></span> 
  
<span data-ttu-id="7d176-151">如果要调用[IAddrBook::P reparerecips](iaddrbook-preparerecips.md), 请确保您传入的列表中的 Exchange 收件人包含的**PR_AB_PROVIDERS**属性包含与通讯簿提供程序相对应的**emsabpUID** 。收件人属于。</span><span class="sxs-lookup"><span data-stu-id="7d176-151">If you are calling [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md), make sure that the Exchange recipients in the list that you pass in contain the **PR_AB_PROVIDERS** property that has the **emsabpUID** that corresponds to the address book provider that the recipient belongs to.</span></span> <span data-ttu-id="7d176-152">调用[IAddrBook:](iaddrbook-preparerecips.md)从[IAddrBook:: ResolveName](iaddrbook-resolvename.md)获取的行上:P reparerecips 不需要其他任何操作, 但某些代码将对仅包含**IAddrBook**的行调用[reparerecips::P PR_ENTRYID](iaddrbook-preparerecips.md)财产.</span><span class="sxs-lookup"><span data-stu-id="7d176-152">Calling [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) on a row that you obtained from [IAddrBook::ResolveName](iaddrbook-resolvename.md) requires no additional action, but some code will call [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) on rows that contain only the **PR_ENTRYID** property.</span></span> <span data-ttu-id="7d176-153">此情况和类似情况中的行都应包含**PR_ENTRYID**和**PR_AB_PROVIDERS** , 并且**PR_AB_PROVIDERS**属性设置为正确的**emsabpUID**。</span><span class="sxs-lookup"><span data-stu-id="7d176-153">Rows in this and similar situations should contain both **PR_ENTRYID** and **PR_AB_PROVIDERS** with the **PR_AB_PROVIDERS** property set to the correct **emsabpUID**.</span></span>
  
<span data-ttu-id="7d176-154">解析多个 Exchange 帐户的过程的简单说明如下:</span><span class="sxs-lookup"><span data-stu-id="7d176-154">A simple description of the process for resolving multiple Exchange accounts is as follows:</span></span>
  
- <span data-ttu-id="7d176-155">如果给定了服务唯一标识符, 您的代码将在**PR_SERVICE_UID**属性的邮件存储区中查找与您拥有的项匹配的表。</span><span class="sxs-lookup"><span data-stu-id="7d176-155">Given the service unique identifier, your code looks in the table of the message store of the **PR_SERVICE_UID** property that matches the one that you have.</span></span> <span data-ttu-id="7d176-156">在这里, 您可以确定正确的**PR_MDB_PROVIDER**。</span><span class="sxs-lookup"><span data-stu-id="7d176-156">From there, you can determine the correct **PR_MDB_PROVIDER**.</span></span> <span data-ttu-id="7d176-157">此行包含适当的存储区。</span><span class="sxs-lookup"><span data-stu-id="7d176-157">This row contains the appropriate store.</span></span>
    
- <span data-ttu-id="7d176-158">在给定**emsmdbUID**的情况下, 您的代码会在邮件服务表中查找公开与**emsmdbUID**匹配的**PidTagExchangeProfileSectionId**的行。</span><span class="sxs-lookup"><span data-stu-id="7d176-158">Given an **emsmdbUID**, your code looks in the message services table for the row that exposes the **PidTagExchangeProfileSectionId** that matches the **emsmdbUID**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7d176-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d176-159">See also</span></span>



[<span data-ttu-id="7d176-160">HrCompareABEntryIDsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="7d176-160">HrCompareABEntryIDsWithExchangeContext</span></span>](hrcompareabentryidswithexchangecontext.md)
  
[<span data-ttu-id="7d176-161">HrDoABDetailsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="7d176-161">HrDoABDetailsWithExchangeContext</span></span>](hrdoabdetailswithexchangecontext.md)
  
[<span data-ttu-id="7d176-162">HrDoABDetailsWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="7d176-162">HrDoABDetailsWithProviderUID</span></span>](hrdoabdetailswithprovideruid.md)
  
[<span data-ttu-id="7d176-163">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="7d176-163">HrGetGALFromEmsmdbUID</span></span>](hrgetgalfromemsmdbuid.md)
  
[<span data-ttu-id="7d176-164">HrOpenABEntryUsingDefaultContext</span><span class="sxs-lookup"><span data-stu-id="7d176-164">HrOpenABEntryUsingDefaultContext</span></span>](hropenabentryusingdefaultcontext.md)
  
[<span data-ttu-id="7d176-165">HrOpenABEntryWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="7d176-165">HrOpenABEntryWithExchangeContext</span></span>](hropenabentrywithexchangecontext.md)
  
[<span data-ttu-id="7d176-166">HrOpenABEntryWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="7d176-166">HrOpenABEntryWithProviderUID</span></span>](hropenabentrywithprovideruid.md)
  
[<span data-ttu-id="7d176-167">HrOpenABEntryWithProviderUIDSupport</span><span class="sxs-lookup"><span data-stu-id="7d176-167">HrOpenABEntryWithProviderUIDSupport</span></span>](hropenabentrywithprovideruidsupport.md)
  
[<span data-ttu-id="7d176-168">HrOpenABEntryWithResolvedRow</span><span class="sxs-lookup"><span data-stu-id="7d176-168">HrOpenABEntryWithResolvedRow</span></span>](hropenabentrywithresolvedrow.md)
  
[<span data-ttu-id="7d176-169">HrOpenABEntryWithSupport</span><span class="sxs-lookup"><span data-stu-id="7d176-169">HrOpenABEntryWithSupport</span></span>](hropenabentrywithsupport.md)
  
[<span data-ttu-id="7d176-170">PidTagExchangeProfileSectionId 规范属性</span><span class="sxs-lookup"><span data-stu-id="7d176-170">PidTagExchangeProfileSectionId Canonical Property</span></span>](pidtagexchangeprofilesectionid-canonical-property.md)


[<span data-ttu-id="7d176-171">如何打开 "全局配置文件" 部分</span><span class="sxs-lookup"><span data-stu-id="7d176-171">How To Open the Global Profile Section</span></span>](https://support.microsoft.com/kb/188482)

