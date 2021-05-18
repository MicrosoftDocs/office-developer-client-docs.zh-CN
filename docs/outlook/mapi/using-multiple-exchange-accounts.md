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
# <a name="using-multiple-exchange-accounts"></a><span data-ttu-id="dff3e-103">使用多个Exchange帐户</span><span class="sxs-lookup"><span data-stu-id="dff3e-103">Using Multiple Exchange Accounts</span></span>

  
  
<span data-ttu-id="dff3e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dff3e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dff3e-105">Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持与多个 Exchange 电子邮件帐户集成。</span><span class="sxs-lookup"><span data-stu-id="dff3e-105">Microsoft Outlook 2010 and Microsoft Outlook 2013 support integration with multiple exchange email accounts.</span></span> <span data-ttu-id="dff3e-106">在 Outlook 2010 或 Outlook 2013 中，用户可以向同一配置文件添加两个 exchange 帐户，并仍享受丰富的 Exchange 功能，如发布的全局地址列表 (GAL) 、Exchange Out-of-Office 配置和文件夹共享。</span><span class="sxs-lookup"><span data-stu-id="dff3e-106">In Outlook 2010 or Outlook 2013, a user could add two exchange accounts to the same profile and still enjoy rich Exchange features such as the published global address list (GAL), Exchange Out-of-Office configuration, and folder sharing.</span></span>
  
<span data-ttu-id="dff3e-107">熟悉 Microsoft Office Outlook 2007 及更早版本 MAPI 配置文件部分的用户知道，Exchange 设置（如电子邮件用户名和服务器名称）存储在固定的 Exchange 全局配置文件部分 **pbGlobalProfileSectionGuid** 中。</span><span class="sxs-lookup"><span data-stu-id="dff3e-107">Those familiar with the MAPI profile sections for Microsoft Office Outlook 2007 and earlier know that Exchange settings, such as the email user name and server name, are stored in the fixed Exchange Global Profile section, **pbGlobalProfileSectionGuid**.</span></span> <span data-ttu-id="dff3e-108">在 Outlook 2010 和 Outlook 2013 中，每个 Exchange 帐户都需要自己的配置文件部分来存储设置，使得 **pbGlobalProfileSectionGuid** 已过时。</span><span class="sxs-lookup"><span data-stu-id="dff3e-108">In Outlook 2010 and Outlook 2013, each Exchange account needs its own profile section to store settings, making the **pbGlobalProfileSectionGuid** obsolete.</span></span> 
  
<span data-ttu-id="dff3e-109">Outlook 2010 和 Outlook 2013 Exchange 设置仍存储在配置文件中，但包含其设置的配置文件节的唯一标识符是按配置文件动态分配的。</span><span class="sxs-lookup"><span data-stu-id="dff3e-109">Outlook 2010 and Outlook 2013 Exchange settings are still stored in the profile, but a unique identifier for the profile section that contains their settings is dynamically allocated per profile.</span></span> <span data-ttu-id="dff3e-110">配置文件中 Exchange 设置的位置存储在[PidTagExchangeProfileSectionId](pidtagexchangeprofilesectionid-canonical-property.md)规范属性中，可在 Exchange 帐户的邮件服务配置文件部分找到该属性。</span><span class="sxs-lookup"><span data-stu-id="dff3e-110">The location of the Exchange settings in the profile is stored in the [PidTagExchangeProfileSectionId Canonical Property](pidtagexchangeprofilesectionid-canonical-property.md), which can be found in the message service profile section of the Exchange account.</span></span> <span data-ttu-id="dff3e-111">此属性还可以在帐户的此邮件服务中每个提供程序的配置文件部分找到。</span><span class="sxs-lookup"><span data-stu-id="dff3e-111">This property can also be found in the profile section for each provider in this message service of the account.</span></span> <span data-ttu-id="dff3e-112">唯一标识符不存储在服务器上，并且跨配置文件将不同。</span><span class="sxs-lookup"><span data-stu-id="dff3e-112">The unique identifier is not stored on the server and will be different across profiles.</span></span>
  
<span data-ttu-id="dff3e-113">Outlook 2010 Outlook 2013 使用 **PidTagExchangeProfileSectionId** 作为唯一标识符来指定 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="dff3e-113">Outlook 2010 and Outlook 2013 use the **PidTagExchangeProfileSectionId** as a unique identifier to specify an Exchange account.</span></span> <span data-ttu-id="dff3e-114">当通过此方式使用时，此唯一标识符称为 **emsmdbUID**。</span><span class="sxs-lookup"><span data-stu-id="dff3e-114">When used in this manner, this unique identifier is known as the **emsmdbUID**.</span></span> <span data-ttu-id="dff3e-115">对于一些 MAPI Outlook操作，可能需要 **emsmdbUID** 来指定操作Exchange帐户。</span><span class="sxs-lookup"><span data-stu-id="dff3e-115">For some MAPI and Outlook operations, an **emsmdbUID** might be required to specify which Exchange account should be used for the operation.</span></span> 
  
<span data-ttu-id="dff3e-116">为了支持多个Exchange帐户，必须在代码中对新函数进行一些调用。</span><span class="sxs-lookup"><span data-stu-id="dff3e-116">In order to support multiple Exchange accounts, you must use some calls to new functions in your code.</span></span> <span data-ttu-id="dff3e-117">将 IMailUser 上使用 **entryID** 和 [IAddrBook：：OpenEntry](iaddrbook-openentry.md)或 [IAddrBook：：CompareEntryIDs](iaddrbook-compareentryids.md)的任何调用替换为以下函数之一 [： IMAPIProp](imailuserimapiprop.md)和 [IDistList ： IMAPIContainer。](idistlistimapicontainer.md)</span><span class="sxs-lookup"><span data-stu-id="dff3e-117">Replace any call that uses an **entryID** and either [IAddrBook::OpenEntry](iaddrbook-openentry.md) or [IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md) on [IMailUser : IMAPIProp](imailuserimapiprop.md) and [IDistList : IMAPIContainer](idistlistimapicontainer.md) with one of the following functions.</span></span> 
  
- [<span data-ttu-id="dff3e-118">HrCompareABEntryIDsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="dff3e-118">HrCompareABEntryIDsWithExchangeContext</span></span>](hrcompareabentryidswithexchangecontext.md)
    
- [<span data-ttu-id="dff3e-119">HrDoABDetailsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="dff3e-119">HrDoABDetailsWithExchangeContext</span></span>](hrdoabdetailswithexchangecontext.md)
    
- [<span data-ttu-id="dff3e-120">HrDoABDetailsWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="dff3e-120">HrDoABDetailsWithProviderUID</span></span>](hrdoabdetailswithprovideruid.md)
    
- [<span data-ttu-id="dff3e-121">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="dff3e-121">HrGetGALFromEmsmdbUID</span></span>](hrgetgalfromemsmdbuid.md)
    
- [<span data-ttu-id="dff3e-122">HrOpenABEntryUsingDefaultContext</span><span class="sxs-lookup"><span data-stu-id="dff3e-122">HrOpenABEntryUsingDefaultContext</span></span>](hropenabentryusingdefaultcontext.md)
    
- [<span data-ttu-id="dff3e-123">HrOpenABEntryWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="dff3e-123">HrOpenABEntryWithExchangeContext</span></span>](hropenabentrywithexchangecontext.md)
    
- [<span data-ttu-id="dff3e-124">HrOpenABEntryWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="dff3e-124">HrOpenABEntryWithProviderUID</span></span>](hropenabentrywithprovideruid.md)
    
- [<span data-ttu-id="dff3e-125">HrOpenABEntryWithProviderUIDSupport</span><span class="sxs-lookup"><span data-stu-id="dff3e-125">HrOpenABEntryWithProviderUIDSupport</span></span>](hropenabentrywithprovideruidsupport.md)
    
- [<span data-ttu-id="dff3e-126">HrOpenABEntryWithResolvedRow</span><span class="sxs-lookup"><span data-stu-id="dff3e-126">HrOpenABEntryWithResolvedRow</span></span>](hropenabentrywithresolvedrow.md)
    
- [<span data-ttu-id="dff3e-127">HrOpenABEntryWithSupport</span><span class="sxs-lookup"><span data-stu-id="dff3e-127">HrOpenABEntryWithSupport</span></span>](hropenabentrywithsupport.md)
    
## <a name="legacy-support"></a><span data-ttu-id="dff3e-128">旧版支持</span><span class="sxs-lookup"><span data-stu-id="dff3e-128">Legacy support</span></span>

<span data-ttu-id="dff3e-129">在新建 **emsmdbUID** 节之前编写的任何 MAPI 客户端仍受支持。</span><span class="sxs-lookup"><span data-stu-id="dff3e-129">Any MAPI clients written before the creation of this new **emsmdbUID** section are still supported.</span></span> <span data-ttu-id="dff3e-130">这些客户端将继续检索上一个全局部分 **pbGlobalProfileSectionGuid**。</span><span class="sxs-lookup"><span data-stu-id="dff3e-130">These clients will continue to retrieve the previous global section, **pbGlobalProfileSectionGuid**.</span></span> <span data-ttu-id="dff3e-131">此配置文件节的查询将重定向到一个Exchange查询的帐户。</span><span class="sxs-lookup"><span data-stu-id="dff3e-131">Queries for this profile section will be redirected to one designated Exchange account that handles legacy inquiries.</span></span> <span data-ttu-id="dff3e-132">通过查看邮件服务表并添加用于处理旧呼叫的列，可以确定处理旧呼叫PR_EMSMDB_LEGACY。</span><span class="sxs-lookup"><span data-stu-id="dff3e-132">The account that handles the legacy calls can be determined by looking at the message service table and adding a column for PR_EMSMDB_LEGACY.</span></span> <span data-ttu-id="dff3e-133">只有一个邮件服务将此设置为 true，其 **PidTagExchangeProfileSectionId** 称为旧 **emsmdbUID**。</span><span class="sxs-lookup"><span data-stu-id="dff3e-133">Only one message service will have this set to true, and its **PidTagExchangeProfileSectionId** is called the legacy **emsmdbUID**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dff3e-134">可配置的 MAPI 设置（如默认存储和默认帐户）对哪个帐户处理旧版呼叫没有影响。</span><span class="sxs-lookup"><span data-stu-id="dff3e-134">Configurable MAPI settings such as the default store and the default account have no effect on which account handles legacy calls.</span></span> <span data-ttu-id="dff3e-135">无法配置处理旧版呼叫的帐户。</span><span class="sxs-lookup"><span data-stu-id="dff3e-135">The account that handles the legacy calls cannot be configured.</span></span> 
  
<span data-ttu-id="dff3e-136">旧 **帐户的 emsmdbUID** 将复制到全局配置文件Outlook中。</span><span class="sxs-lookup"><span data-stu-id="dff3e-136">The **emsmdbUID** of the legacy account is copied to the Outlook Global Profile Section.</span></span> <span data-ttu-id="dff3e-137">如果此属性不存在，则查询邮件服务表将确定哪个帐户是旧处理程序，并设置"全局配置文件"Outlook的值。</span><span class="sxs-lookup"><span data-stu-id="dff3e-137">If this property does not exist, querying for the message services table will determine what account is the legacy handler and set the value in the Outlook Global Profile Section.</span></span> 
  
<span data-ttu-id="dff3e-138">很明显，Outlook Global Profile Section 不同于 Exchange Global Profile Section，在 Outlook 2010 和 Outlook 2013 中，Exchange Global Profile Section 不再真正全局，因为您可以有多个 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="dff3e-138">To be clear, the Outlook Global Profile Section differs from the Exchange Global Profile Section, and in Outlook 2010 and Outlook 2013 the Exchange Global Profile Section is no longer really global because you can have multiple Exchange accounts.</span></span> <span data-ttu-id="dff3e-139">"Outlook配置文件"部分包含有关Outlook的属性，如文件夹 MRU 的状态或全局连接的状态。</span><span class="sxs-lookup"><span data-stu-id="dff3e-139">The Outlook Global Profile section contains properties about Outlook, such as the state of the folder MRU or the state of the global connection.</span></span>
  
## <a name="address-book-account-contexts"></a><span data-ttu-id="dff3e-140">通讯簿帐户上下文</span><span class="sxs-lookup"><span data-stu-id="dff3e-140">Address Book Account Contexts</span></span>

<span data-ttu-id="dff3e-141">若要正确解析多个 Exchange 帐户的地址，请使用采用帐户上下文的新函数，以便对通讯簿的调用搜索正确的 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="dff3e-141">To resolve addresses correctly with multiple Exchange accounts, use the new functions that take an account context so that calls to the address book search the correct Exchange account.</span></span>
  
<span data-ttu-id="dff3e-142">以前的一些通讯簿 API 已弃用，因为 API 并非完全具有多个Exchange功能。</span><span class="sxs-lookup"><span data-stu-id="dff3e-142">Some previous address book APIs were deprecated because the APIs were not fully multiple Exchange capable.</span></span> <span data-ttu-id="dff3e-143">此帐户上下文通常为 **emsmdbUID**。</span><span class="sxs-lookup"><span data-stu-id="dff3e-143">This account context is usually an **emsmdbUID**.</span></span>
  
<span data-ttu-id="dff3e-144">除了 **emsmdbUID** 之外，多个Exchange还具有 **emsabpUID**。</span><span class="sxs-lookup"><span data-stu-id="dff3e-144">In addition to the **emsmdbUID**, multiple Exchange accounts also have an **emsabpUID**.</span></span>
  
1. <span data-ttu-id="dff3e-145">**emsmdbUID** 值标识帐户上下文。</span><span class="sxs-lookup"><span data-stu-id="dff3e-145">The **emsmdbUID** value identifies the account context.</span></span> 
    
2. <span data-ttu-id="dff3e-146">**emsabpUID** 值标识Exchange提供程序。</span><span class="sxs-lookup"><span data-stu-id="dff3e-146">The **emsabpUID** value identifies an Exchange address book provider.</span></span> 
    
<span data-ttu-id="dff3e-147">在解析收件人时，通常使用 **emsabpUID** 值。</span><span class="sxs-lookup"><span data-stu-id="dff3e-147">The **emsabpUID** value is typically used when resolving a recipient.</span></span> <span data-ttu-id="dff3e-148">使用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md)解析收件人时，Exchange行包含 **PR_AB_PROVIDERS** (0x3D010102) 属性，其中包含 **emsabpUID** 值。</span><span class="sxs-lookup"><span data-stu-id="dff3e-148">When resolving a recipient using [IAddrBook::ResolveName](iaddrbook-resolvename.md), an Exchange recipient row contains the **PR_AB_PROVIDERS** (0x3D010102) property, which contains the **emsabpUID** value.</span></span> <span data-ttu-id="dff3e-149">此 **emsabpUID** 值标识Exchange收件人的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="dff3e-149">This **emsabpUID** value identifies the Exchange address book provider for the specific recipient.</span></span> 
  
<span data-ttu-id="dff3e-150">如果要确定特定 **emsmdbUID** 的 **emsabpUID** 值，请打开 **emsmdbUID** 的配置文件部分，并获取 **PR_EMSABP_USER_UID** (0x0x3D1A0102) 属性。</span><span class="sxs-lookup"><span data-stu-id="dff3e-150">If you want to determine the **emsabpUID** value for a particular **emsmdbUID**, open up the profile section for the **emsmdbUID** and get the **PR_EMSABP_USER_UID** (0x0x3D1A0102) property.</span></span> 
  
<span data-ttu-id="dff3e-151">如果要调用 [IAddrBook：:P repareRecips，](iaddrbook-preparerecips.md)请确保所传递列表中的 Exchange 收件人包含与收件人所属的通讯簿提供程序对应的 **emsabpUID** 的 **PR_AB_PROVIDERS** 属性。</span><span class="sxs-lookup"><span data-stu-id="dff3e-151">If you are calling [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md), make sure that the Exchange recipients in the list that you pass in contain the **PR_AB_PROVIDERS** property that has the **emsabpUID** that corresponds to the address book provider that the recipient belongs to.</span></span> <span data-ttu-id="dff3e-152">对从 [IAddrBook：：ResolveName](iaddrbook-resolvename.md)获取的行调用 [IAddrBook：:P repareRecips](iaddrbook-preparerecips.md)无需任何其他操作，但某些代码将在仅包含 **PR_ENTRYID** 属性的行上调用 [IAddrBook：:P repareRecips。](iaddrbook-preparerecips.md)</span><span class="sxs-lookup"><span data-stu-id="dff3e-152">Calling [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) on a row that you obtained from [IAddrBook::ResolveName](iaddrbook-resolvename.md) requires no additional action, but some code will call [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) on rows that contain only the **PR_ENTRYID** property.</span></span> <span data-ttu-id="dff3e-153">此情况及类似情况下的行 **应包含** PR_ENTRYID 和 **PR_AB_PROVIDERS，PR_AB_PROVIDERS\*\*\*\*属性设置为** 正确的 **emsabpUID**。</span><span class="sxs-lookup"><span data-stu-id="dff3e-153">Rows in this and similar situations should contain both **PR_ENTRYID** and **PR_AB_PROVIDERS** with the **PR_AB_PROVIDERS** property set to the correct **emsabpUID**.</span></span>
  
<span data-ttu-id="dff3e-154">解析多个帐户的过程的简单Exchange如下：</span><span class="sxs-lookup"><span data-stu-id="dff3e-154">A simple description of the process for resolving multiple Exchange accounts is as follows:</span></span>
  
- <span data-ttu-id="dff3e-155">在给定服务唯一标识符后，代码将查找与拥有的属性匹配的 **PR_SERVICE_UID** 属性的邮件存储表。</span><span class="sxs-lookup"><span data-stu-id="dff3e-155">Given the service unique identifier, your code looks in the table of the message store of the **PR_SERVICE_UID** property that matches the one that you have.</span></span> <span data-ttu-id="dff3e-156">你可以从该位置确定 **正确的PR_MDB_PROVIDER。**</span><span class="sxs-lookup"><span data-stu-id="dff3e-156">From there, you can determine the correct **PR_MDB_PROVIDER**.</span></span> <span data-ttu-id="dff3e-157">此行包含相应的存储区。</span><span class="sxs-lookup"><span data-stu-id="dff3e-157">This row contains the appropriate store.</span></span>
    
- <span data-ttu-id="dff3e-158">在 **给定 emsmdbUID** 后，您的代码在邮件服务表中查找公开与 **emsmdbUID** 匹配的 **PidTagExchangeProfileSectionId** 的行。</span><span class="sxs-lookup"><span data-stu-id="dff3e-158">Given an **emsmdbUID**, your code looks in the message services table for the row that exposes the **PidTagExchangeProfileSectionId** that matches the **emsmdbUID**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dff3e-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dff3e-159">See also</span></span>



[<span data-ttu-id="dff3e-160">HrCompareABEntryIDsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="dff3e-160">HrCompareABEntryIDsWithExchangeContext</span></span>](hrcompareabentryidswithexchangecontext.md)
  
[<span data-ttu-id="dff3e-161">HrDoABDetailsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="dff3e-161">HrDoABDetailsWithExchangeContext</span></span>](hrdoabdetailswithexchangecontext.md)
  
[<span data-ttu-id="dff3e-162">HrDoABDetailsWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="dff3e-162">HrDoABDetailsWithProviderUID</span></span>](hrdoabdetailswithprovideruid.md)
  
[<span data-ttu-id="dff3e-163">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="dff3e-163">HrGetGALFromEmsmdbUID</span></span>](hrgetgalfromemsmdbuid.md)
  
[<span data-ttu-id="dff3e-164">HrOpenABEntryUsingDefaultContext</span><span class="sxs-lookup"><span data-stu-id="dff3e-164">HrOpenABEntryUsingDefaultContext</span></span>](hropenabentryusingdefaultcontext.md)
  
[<span data-ttu-id="dff3e-165">HrOpenABEntryWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="dff3e-165">HrOpenABEntryWithExchangeContext</span></span>](hropenabentrywithexchangecontext.md)
  
[<span data-ttu-id="dff3e-166">HrOpenABEntryWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="dff3e-166">HrOpenABEntryWithProviderUID</span></span>](hropenabentrywithprovideruid.md)
  
[<span data-ttu-id="dff3e-167">HrOpenABEntryWithProviderUIDSupport</span><span class="sxs-lookup"><span data-stu-id="dff3e-167">HrOpenABEntryWithProviderUIDSupport</span></span>](hropenabentrywithprovideruidsupport.md)
  
[<span data-ttu-id="dff3e-168">HrOpenABEntryWithResolvedRow</span><span class="sxs-lookup"><span data-stu-id="dff3e-168">HrOpenABEntryWithResolvedRow</span></span>](hropenabentrywithresolvedrow.md)
  
[<span data-ttu-id="dff3e-169">HrOpenABEntryWithSupport</span><span class="sxs-lookup"><span data-stu-id="dff3e-169">HrOpenABEntryWithSupport</span></span>](hropenabentrywithsupport.md)
  
[<span data-ttu-id="dff3e-170">PidTagExchangeProfileSectionId 规范属性</span><span class="sxs-lookup"><span data-stu-id="dff3e-170">PidTagExchangeProfileSectionId Canonical Property</span></span>](pidtagexchangeprofilesectionid-canonical-property.md)


[<span data-ttu-id="dff3e-171">如何打开"全局配置文件"部分</span><span class="sxs-lookup"><span data-stu-id="dff3e-171">How To Open the Global Profile Section</span></span>](https://support.microsoft.com/kb/188482)

