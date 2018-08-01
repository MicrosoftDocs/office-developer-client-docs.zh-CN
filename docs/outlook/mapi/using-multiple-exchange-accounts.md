---
title: 使用多个 Exchange 帐户
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4e1804bf-4c50-4942-a7ab-9a8caf1be7e5
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: d5798f4836f6b5635c8e04bd380e53ade34384a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779073"
---
# <a name="using-multiple-exchange-accounts"></a><span data-ttu-id="42790-103">使用多个 Exchange 帐户</span><span class="sxs-lookup"><span data-stu-id="42790-103">Using Multiple Exchange Accounts</span></span>

  
  
<span data-ttu-id="42790-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="42790-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="42790-105">Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持多个 exchange 电子邮件帐户与集成。</span><span class="sxs-lookup"><span data-stu-id="42790-105">Microsoft Outlook 2010 and Microsoft Outlook 2013 support integration with multiple exchange email accounts.</span></span> <span data-ttu-id="42790-106">在 Outlook 2010 或 Outlook 2013 中，用户无法将两个 exchange 帐户添加到的同一配置文件和仍享受丰富的 Exchange 功能，如已发布的全局地址列表 (GAL)、 Exchange 出的 Office 配置和文件夹共享。</span><span class="sxs-lookup"><span data-stu-id="42790-106">In Outlook 2010 or Outlook 2013, a user could add two exchange accounts to the same profile and still enjoy rich Exchange features such as the published global address list (GAL), Exchange Out-of-Office configuration, and folder sharing.</span></span>
  
<span data-ttu-id="42790-107">这些熟悉 Microsoft Office Outlook 2007 MAPI 配置文件部分和早期版本知道，在固定 Exchange 全局配置文件部分**pbGlobalProfileSectionGuid**存储 Exchange 设置，如电子邮件用户的名称和服务器名称。</span><span class="sxs-lookup"><span data-stu-id="42790-107">Those familiar with the MAPI profile sections for Microsoft Office Outlook 2007 and earlier know that Exchange settings, such as the email user name and server name, are stored in the fixed Exchange Global Profile section, **pbGlobalProfileSectionGuid**.</span></span> <span data-ttu-id="42790-108">有关 Exchange 全局配置文件的详细信息，请参阅[如何打开全局配置文件部分](http://support.microsoft.com/kb/188482)。</span><span class="sxs-lookup"><span data-stu-id="42790-108">For more information about the Exchange Global Profile, see [How To Open the Global Profile Section](http://support.microsoft.com/kb/188482).</span></span> <span data-ttu-id="42790-109">在 Outlook 2010 和 Outlook 2013 中，每个 Exchange 帐户需要其自己的配置文件一节来存储设置，使**pbGlobalProfileSectionGuid**已过时。</span><span class="sxs-lookup"><span data-stu-id="42790-109">In Outlook 2010 and Outlook 2013, each Exchange account needs its own profile section to store settings, making the **pbGlobalProfileSectionGuid** obsolete.</span></span> 
  
<span data-ttu-id="42790-110">Outlook 2010 和 Outlook 2013 Exchange 设置仍存储在配置文件，但包含其设置的配置文件内容的唯一标识符动态分配每个配置文件。</span><span class="sxs-lookup"><span data-stu-id="42790-110">Outlook 2010 and Outlook 2013 Exchange settings are still stored in the profile, but a unique identifier for the profile section that contains their settings is dynamically allocated per profile.</span></span> <span data-ttu-id="42790-111">配置文件中的 Exchange 设置的位置存储在[PidTagExchangeProfileSectionId 规范属性](pidtagexchangeprofilesectionid-canonical-property.md)，可以在 Exchange 帐户的邮件服务配置文件部分中找到。</span><span class="sxs-lookup"><span data-stu-id="42790-111">The location of the Exchange settings in the profile is stored in the [PidTagExchangeProfileSectionId Canonical Property](pidtagexchangeprofilesectionid-canonical-property.md), which can be found in the message service profile section of the Exchange account.</span></span> <span data-ttu-id="42790-112">此属性也找不在配置文件部分中的帐户的此消息服务的每个提供程序。</span><span class="sxs-lookup"><span data-stu-id="42790-112">This property can also be found in the profile section for each provider in this message service of the account.</span></span> <span data-ttu-id="42790-113">唯一标识符不存储在服务器上，将配置文件跨不同。</span><span class="sxs-lookup"><span data-stu-id="42790-113">The unique identifier is not stored on the server and will be different across profiles.</span></span>
  
<span data-ttu-id="42790-114">Outlook 2010 和 Outlook 2013 使用**PidTagExchangeProfileSectionId**作为唯一标识符指定 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="42790-114">Outlook 2010 and Outlook 2013 use the **PidTagExchangeProfileSectionId** as a unique identifier to specify an Exchange account.</span></span> <span data-ttu-id="42790-115">在这种方式使用时，此唯一标识符称为**emsmdbUID**。</span><span class="sxs-lookup"><span data-stu-id="42790-115">When used in this manner, this unique identifier is known as the **emsmdbUID**.</span></span> <span data-ttu-id="42790-116">对于某些 MAPI 和 Outlook 的操作， **emsmdbUID**可能需要指定的 Exchange 帐户应使用此操作。</span><span class="sxs-lookup"><span data-stu-id="42790-116">For some MAPI and Outlook operations, an **emsmdbUID** might be required to specify which Exchange account should be used for the operation.</span></span> 
  
<span data-ttu-id="42790-117">为了支持多个 Exchange 帐户，您必须在代码中使用一些新函数的调用。</span><span class="sxs-lookup"><span data-stu-id="42790-117">In order to support multiple Exchange accounts, you must use some calls to new functions in your code.</span></span> <span data-ttu-id="42790-118">使用**entryID**和[IAddrBook::OpenEntry](iaddrbook-openentry.md)或[IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md)任何调用替换[IMailUser: IMAPIProp](imailuserimapiprop.md)和[IDistList: IMAPIContainer](idistlistimapicontainer.md)具有以下函数之一。</span><span class="sxs-lookup"><span data-stu-id="42790-118">Replace any call that uses an **entryID** and either [IAddrBook::OpenEntry](iaddrbook-openentry.md) or [IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md) on [IMailUser : IMAPIProp](imailuserimapiprop.md) and [IDistList : IMAPIContainer](idistlistimapicontainer.md) with one of the following functions.</span></span> 
  
- [<span data-ttu-id="42790-119">HrCompareABEntryIDsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="42790-119">HrCompareABEntryIDsWithExchangeContext</span></span>](hrcompareabentryidswithexchangecontext.md)
    
- [<span data-ttu-id="42790-120">HrDoABDetailsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="42790-120">HrDoABDetailsWithExchangeContext</span></span>](hrdoabdetailswithexchangecontext.md)
    
- [<span data-ttu-id="42790-121">HrDoABDetailsWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="42790-121">HrDoABDetailsWithProviderUID</span></span>](hrdoabdetailswithprovideruid.md)
    
- [<span data-ttu-id="42790-122">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="42790-122">HrGetGALFromEmsmdbUID</span></span>](hrgetgalfromemsmdbuid.md)
    
- [<span data-ttu-id="42790-123">HrOpenABEntryUsingDefaultContext</span><span class="sxs-lookup"><span data-stu-id="42790-123">HrOpenABEntryUsingDefaultContext</span></span>](hropenabentryusingdefaultcontext.md)
    
- [<span data-ttu-id="42790-124">HrOpenABEntryWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="42790-124">HrOpenABEntryWithExchangeContext</span></span>](hropenabentrywithexchangecontext.md)
    
- [<span data-ttu-id="42790-125">HrOpenABEntryWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="42790-125">HrOpenABEntryWithProviderUID</span></span>](hropenabentrywithprovideruid.md)
    
- [<span data-ttu-id="42790-126">HrOpenABEntryWithProviderUIDSupport</span><span class="sxs-lookup"><span data-stu-id="42790-126">HrOpenABEntryWithProviderUIDSupport</span></span>](hropenabentrywithprovideruidsupport.md)
    
- [<span data-ttu-id="42790-127">HrOpenABEntryWithResolvedRow</span><span class="sxs-lookup"><span data-stu-id="42790-127">HrOpenABEntryWithResolvedRow</span></span>](hropenabentrywithresolvedrow.md)
    
- [<span data-ttu-id="42790-128">HrOpenABEntryWithSupport</span><span class="sxs-lookup"><span data-stu-id="42790-128">HrOpenABEntryWithSupport</span></span>](hropenabentrywithsupport.md)
    
## <a name="legacy-support"></a><span data-ttu-id="42790-129">旧的支持</span><span class="sxs-lookup"><span data-stu-id="42790-129">Legacy support</span></span>

<span data-ttu-id="42790-130">仍然支持之前创建的此新**emsmdbUID**部分写入任何 MAPI 客户端。</span><span class="sxs-lookup"><span data-stu-id="42790-130">Any MAPI clients written before the creation of this new **emsmdbUID** section are still supported.</span></span> <span data-ttu-id="42790-131">这些客户端将继续检索以前全局节**pbGlobalProfileSectionGuid**。</span><span class="sxs-lookup"><span data-stu-id="42790-131">These clients will continue to retrieve the previous global section, **pbGlobalProfileSectionGuid**.</span></span> <span data-ttu-id="42790-132">此配置文件部分的查询将重定向到一个处理旧的查询的指定 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="42790-132">Queries for this profile section will be redirected to one designated Exchange account that handles legacy inquiries.</span></span> <span data-ttu-id="42790-133">可以通过查看邮件服务表并将列添加的 PR_EMSMDB_LEGACY 确定处理旧的呼叫的帐户。</span><span class="sxs-lookup"><span data-stu-id="42790-133">The account that handles the legacy calls can be determined by looking at the message service table and adding a column for PR_EMSMDB_LEGACY.</span></span> <span data-ttu-id="42790-134">只有一个邮件服务可以设置为 true，则和其**PidTagExchangeProfileSectionId**这称为旧版**emsmdbUID**。</span><span class="sxs-lookup"><span data-stu-id="42790-134">Only one message service will have this set to true, and its **PidTagExchangeProfileSectionId** is called the legacy **emsmdbUID**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42790-135">可配置的 MAPI 设置，如默认存储和默认帐户具有帐户在其处理旧的呼叫没有影响。</span><span class="sxs-lookup"><span data-stu-id="42790-135">Configurable MAPI settings such as the default store and the default account have no effect on which account handles legacy calls.</span></span> <span data-ttu-id="42790-136">处理旧式呼叫的帐户不能配置。</span><span class="sxs-lookup"><span data-stu-id="42790-136">The account that handles the legacy calls cannot be configured.</span></span> 
  
<span data-ttu-id="42790-137">旧式帐户**emsmdbUID**复制到 Outlook 全局配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="42790-137">The **emsmdbUID** of the legacy account is copied to the Outlook Global Profile Section.</span></span> <span data-ttu-id="42790-138">如果该属性不存在，消息服务表中的查询将确定哪个帐户是旧的处理程序，并将值设置的 Outlook 全局配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="42790-138">If this property does not exist, querying for the message services table will determine what account is the legacy handler and set the value in the Outlook Global Profile Section.</span></span> 
  
<span data-ttu-id="42790-139">若要清除，Outlook 全局配置文件部分不同从 Exchange 全局配置文件部分中，并且在 Outlook 2010 和 Outlook 2013 中 Exchange 全局配置文件部分不再真正全局因为可以有多个 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="42790-139">To be clear, the Outlook Global Profile Section differs from the Exchange Global Profile Section, and in Outlook 2010 and Outlook 2013 the Exchange Global Profile Section is no longer really global because you can have multiple Exchange accounts.</span></span> <span data-ttu-id="42790-140">Outlook 全局配置文件部分包含有关 Outlook，如文件夹 MRU 的状态或全局连接状态的属性。</span><span class="sxs-lookup"><span data-stu-id="42790-140">The Outlook Global Profile section contains properties about Outlook, such as the state of the folder MRU or the state of the global connection.</span></span>
  
## <a name="address-book-account-contexts"></a><span data-ttu-id="42790-141">通讯簿帐户上下文</span><span class="sxs-lookup"><span data-stu-id="42790-141">Address Book Account Contexts</span></span>

<span data-ttu-id="42790-142">若要解决正确使用多个 Exchange 帐户的地址，请使用拍摄帐户上下文，以便调用通讯簿搜索正确的 Exchange 帐户的新功能。</span><span class="sxs-lookup"><span data-stu-id="42790-142">To resolve addresses correctly with multiple Exchange accounts, use the new functions that take an account context so that calls to the address book search the correct Exchange account.</span></span>
  
<span data-ttu-id="42790-143">因为 Api 未能够完全多个 Exchange 否决的 Api 某些以前通讯簿。</span><span class="sxs-lookup"><span data-stu-id="42790-143">Some previous address book APIs were deprecated because the APIs were not fully multiple Exchange capable.</span></span> <span data-ttu-id="42790-144">此帐户上下文通常是**emsmdbUID**。</span><span class="sxs-lookup"><span data-stu-id="42790-144">This account context is usually an **emsmdbUID**.</span></span>
  
<span data-ttu-id="42790-145">除了**emsmdbUID**，多个 Exchange 帐户还有**emsabpUID**。</span><span class="sxs-lookup"><span data-stu-id="42790-145">In addition to the **emsmdbUID**, multiple Exchange accounts also have an **emsabpUID**.</span></span>
  
1. <span data-ttu-id="42790-146">**EmsmdbUID**值标识的帐户上下文。</span><span class="sxs-lookup"><span data-stu-id="42790-146">The **emsmdbUID** value identifies the account context.</span></span> 
    
2. <span data-ttu-id="42790-147">**EmsabpUID**值标识 Exchange 通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="42790-147">The **emsabpUID** value identifies an Exchange address book provider.</span></span> 
    
<span data-ttu-id="42790-148">解析收件人时通常使用**emsabpUID**值。</span><span class="sxs-lookup"><span data-stu-id="42790-148">The **emsabpUID** value is typically used when resolving a recipient.</span></span> <span data-ttu-id="42790-149">解析收件人使用[IAddrBook::ResolveName](iaddrbook-resolvename.md)时, Exchange 收件人行包含**PR_AB_PROVIDERS** (0x3D010102) 属性，其中包含**emsabpUID**值。</span><span class="sxs-lookup"><span data-stu-id="42790-149">When resolving a recipient using [IAddrBook::ResolveName](iaddrbook-resolvename.md), an Exchange recipient row contains the **PR_AB_PROVIDERS** (0x3D010102) property, which contains the **emsabpUID** value.</span></span> <span data-ttu-id="42790-150">此**emsabpUID**值标识 Exchange 通讯簿提供程序特定的收件人。</span><span class="sxs-lookup"><span data-stu-id="42790-150">This **emsabpUID** value identifies the Exchange address book provider for the specific recipient.</span></span> 
  
<span data-ttu-id="42790-151">如果您想要确定特定**emsmdbUID** **emsabpUID**值，打开配置文件部分的**emsmdbUID**并获取**PR_EMSABP_USER_UID** (0x0x3D1A0102) 属性。</span><span class="sxs-lookup"><span data-stu-id="42790-151">If you want to determine the **emsabpUID** value for a particular **emsmdbUID**, open up the profile section for the **emsmdbUID** and get the **PR_EMSABP_USER_UID** (0x0x3D1A0102) property.</span></span> 
  
<span data-ttu-id="42790-152">如果您正在呼叫[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)，请确保您传入的列表中的 Exchange 收件人包含具有**emsabpUID**对应于通讯簿提供程序的**PR_AB_PROVIDERS**属性的收件人所属。</span><span class="sxs-lookup"><span data-stu-id="42790-152">If you are calling [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md), make sure that the Exchange recipients in the list that you pass in contain the **PR_AB_PROVIDERS** property that has the **emsabpUID** that corresponds to the address book provider that the recipient belongs to.</span></span> <span data-ttu-id="42790-153">对从[IAddrBook::ResolveName](iaddrbook-resolvename.md)获得的行调用[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)不需要其他操作，但某些代码将在包含仅**PR_ENTRYID**的行上调用[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)属性。</span><span class="sxs-lookup"><span data-stu-id="42790-153">Calling [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) on a row that you obtained from [IAddrBook::ResolveName](iaddrbook-resolvename.md) requires no additional action, but some code will call [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) on rows that contain only the **PR_ENTRYID** property.</span></span> <span data-ttu-id="42790-154">在此行，并且类似的情况下应包含**PR_ENTRYID**和**PR_AB_PROVIDERS** **PR_AB_PROVIDERS**属性设置为正确**emsabpUID**。</span><span class="sxs-lookup"><span data-stu-id="42790-154">Rows in this and similar situations should contain both **PR_ENTRYID** and **PR_AB_PROVIDERS** with the **PR_AB_PROVIDERS** property set to the correct **emsabpUID**.</span></span>
  
<span data-ttu-id="42790-155">简单的解析多个 Exchange 帐户的过程说明如下所示：</span><span class="sxs-lookup"><span data-stu-id="42790-155">A simple description of the process for resolving multiple Exchange accounts is as follows:</span></span>
  
- <span data-ttu-id="42790-156">给定的服务的唯一标识符， **PR_SERVICE_UID**属性必须一匹配的邮件存储的表中查找您的代码。</span><span class="sxs-lookup"><span data-stu-id="42790-156">Given the service unique identifier, your code looks in the table of the message store of the **PR_SERVICE_UID** property that matches the one that you have.</span></span> <span data-ttu-id="42790-157">从，您可以确定正确的**PR_MDB_PROVIDER**。</span><span class="sxs-lookup"><span data-stu-id="42790-157">From there, you can determine the correct **PR_MDB_PROVIDER**.</span></span> <span data-ttu-id="42790-158">此行包含在相应的商店。</span><span class="sxs-lookup"><span data-stu-id="42790-158">This row contains the appropriate store.</span></span>
    
- <span data-ttu-id="42790-159">给定**emsmdbUID**，在消息服务表中的行的公开匹配**emsmdbUID** **PidTagExchangeProfileSectionId**中查找您的代码。</span><span class="sxs-lookup"><span data-stu-id="42790-159">Given an **emsmdbUID**, your code looks in the message services table for the row that exposes the **PidTagExchangeProfileSectionId** that matches the **emsmdbUID**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="42790-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42790-160">See also</span></span>



[<span data-ttu-id="42790-161">HrCompareABEntryIDsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="42790-161">HrCompareABEntryIDsWithExchangeContext</span></span>](hrcompareabentryidswithexchangecontext.md)
  
[<span data-ttu-id="42790-162">HrDoABDetailsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="42790-162">HrDoABDetailsWithExchangeContext</span></span>](hrdoabdetailswithexchangecontext.md)
  
[<span data-ttu-id="42790-163">HrDoABDetailsWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="42790-163">HrDoABDetailsWithProviderUID</span></span>](hrdoabdetailswithprovideruid.md)
  
[<span data-ttu-id="42790-164">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="42790-164">HrGetGALFromEmsmdbUID</span></span>](hrgetgalfromemsmdbuid.md)
  
[<span data-ttu-id="42790-165">HrOpenABEntryUsingDefaultContext</span><span class="sxs-lookup"><span data-stu-id="42790-165">HrOpenABEntryUsingDefaultContext</span></span>](hropenabentryusingdefaultcontext.md)
  
[<span data-ttu-id="42790-166">HrOpenABEntryWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="42790-166">HrOpenABEntryWithExchangeContext</span></span>](hropenabentrywithexchangecontext.md)
  
[<span data-ttu-id="42790-167">HrOpenABEntryWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="42790-167">HrOpenABEntryWithProviderUID</span></span>](hropenabentrywithprovideruid.md)
  
[<span data-ttu-id="42790-168">HrOpenABEntryWithProviderUIDSupport</span><span class="sxs-lookup"><span data-stu-id="42790-168">HrOpenABEntryWithProviderUIDSupport</span></span>](hropenabentrywithprovideruidsupport.md)
  
[<span data-ttu-id="42790-169">HrOpenABEntryWithResolvedRow</span><span class="sxs-lookup"><span data-stu-id="42790-169">HrOpenABEntryWithResolvedRow</span></span>](hropenabentrywithresolvedrow.md)
  
[<span data-ttu-id="42790-170">HrOpenABEntryWithSupport</span><span class="sxs-lookup"><span data-stu-id="42790-170">HrOpenABEntryWithSupport</span></span>](hropenabentrywithsupport.md)
  
[<span data-ttu-id="42790-171">PidTagExchangeProfileSectionId 规范属性</span><span class="sxs-lookup"><span data-stu-id="42790-171">PidTagExchangeProfileSectionId Canonical Property</span></span>](pidtagexchangeprofilesectionid-canonical-property.md)


[<span data-ttu-id="42790-172">如何打开全局配置文件部分</span><span class="sxs-lookup"><span data-stu-id="42790-172">How To Open the Global Profile Section</span></span>](http://support.microsoft.com/kb/188482)

