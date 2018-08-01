---
title: 关于帐户管理 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: eb6b921d-ecf8-3ce5-87ba-ac1632416b05
description: 帐户管理 API 提供访问帐户信息，并支持帐户更改的通知。 此 api 的客户端，为邮件提供程序执行以下操作：
ms.openlocfilehash: 678143def25395c47f1c17cc99dcdcd1fb145e1c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774166"
---
# <a name="about-the-account-management-api"></a><span data-ttu-id="0c806-104">关于帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="0c806-104">About the Account Management API</span></span>

<span data-ttu-id="0c806-105">帐户管理 API 提供访问帐户信息，并支持帐户更改的通知。</span><span class="sxs-lookup"><span data-stu-id="0c806-105">The Account Management API provides access to account information and supports notifications of account changes.</span></span> <span data-ttu-id="0c806-106">此 api 的客户端，为邮件提供程序执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c806-106">As clients of this API, mail providers do the following:</span></span>
  
1. <span data-ttu-id="0c806-107">使用[IOlkAccountManager](iolkaccountmanager.md)管理帐户的访问权并设置有关帐户更改的通知。</span><span class="sxs-lookup"><span data-stu-id="0c806-107">Use [IOlkAccountManager](iolkaccountmanager.md) to manage access to accounts and set up notifications about account changes.</span></span> 
    
2. <span data-ttu-id="0c806-108">实现和使用[IOlkAccountNotify](iolkaccountnotify.md)发送有关帐户更改的通知。</span><span class="sxs-lookup"><span data-stu-id="0c806-108">Implement and use [IOlkAccountNotify](iolkaccountnotify.md) to send notifications about account changes.</span></span> 
    
3. <span data-ttu-id="0c806-109">使用[IOlkEnum](iolkenum.md)枚举帐户。</span><span class="sxs-lookup"><span data-stu-id="0c806-109">Use [IOlkEnum](iolkenum.md) to enumerate accounts.</span></span> 
    
4. <span data-ttu-id="0c806-110">使用[IOlkAccount](iolkaccount.md)可获取和设置属性和帐户的其他信息。</span><span class="sxs-lookup"><span data-stu-id="0c806-110">Use [IOlkAccount](iolkaccount.md) to get and set properties and other information about an account.</span></span> <span data-ttu-id="0c806-111">客户端获取[IOlkAccountManager::FindAccount](iolkaccountmanager-findaccount.md)或[IOlkEnum::GetNext](iolkenum-getnext.md)访问个人帐户通过该接口。</span><span class="sxs-lookup"><span data-stu-id="0c806-111">Clients obtain this interface through [IOlkAccountManager::FindAccount](iolkaccountmanager-findaccount.md) or [IOlkEnum::GetNext](iolkenum-getnext.md) to access an individual account.</span></span> 
    
5. <span data-ttu-id="0c806-112">实现和使用[IOlkAccountHelper](iolkaccounthelper.md)提供帐户管理器帮助程序功能，包括帐户配置文件的名称和当前的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="0c806-112">Implement and use [IOlkAccountHelper](iolkaccounthelper.md) to provide the account manager helper functionality, including getting an account's profile name and the current MAPI session.</span></span> 
    
6. <span data-ttu-id="0c806-113">实现和使用[IOlkErrorUnknown](iolkerrorunknown.md)提供有关在**IOlkAccountManager**、 **IOlkAccountNotify**和**IOlkAccount**错误的额外信息。</span><span class="sxs-lookup"><span data-stu-id="0c806-113">Implement and use [IOlkErrorUnknown](iolkerrorunknown.md) to provide extra information about an error in **IOlkAccountManager**, **IOlkAccountNotify**, and **IOlkAccount**.</span></span> 

##  <a name="account-management-api-components"></a><span data-ttu-id="0c806-114">帐户管理 API 组件</span><span class="sxs-lookup"><span data-stu-id="0c806-114">Account Management API components</span></span>

<span data-ttu-id="0c806-115">帐户管理 API 提供了以下定义数据类型、 接口、 名为属性和属性。</span><span class="sxs-lookup"><span data-stu-id="0c806-115">The Account Management API provides the following definitions, data types, interfaces, named properties, and properties.</span></span>
  
### <a name="definitions"></a><span data-ttu-id="0c806-116">定义</span><span class="sxs-lookup"><span data-stu-id="0c806-116">Definitions</span></span>
  
- [<span data-ttu-id="0c806-117">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="0c806-117">Constants (Account management API)</span></span>](constants-account-management-api.md)
    
### <a name="data-types"></a><span data-ttu-id="0c806-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="0c806-118">Data types</span></span>
  
- [<span data-ttu-id="0c806-119">ACCT_BIN</span><span class="sxs-lookup"><span data-stu-id="0c806-119">ACCT_BIN</span></span>](acct_bin.md)
    
- [<span data-ttu-id="0c806-120">ACCT_VARIANT</span><span class="sxs-lookup"><span data-stu-id="0c806-120">ACCT_VARIANT</span></span>](acct_variant.md)
    
### <a name="interfaces"></a><span data-ttu-id="0c806-121">接口</span><span class="sxs-lookup"><span data-stu-id="0c806-121">Interfaces</span></span>
  
- [<span data-ttu-id="0c806-122">IOlkAccount</span><span class="sxs-lookup"><span data-stu-id="0c806-122">IOlkAccount</span></span>](iolkaccount.md)
    
- [<span data-ttu-id="0c806-123">IOlkAccountHelper</span><span class="sxs-lookup"><span data-stu-id="0c806-123">IOlkAccountHelper</span></span>](iolkaccounthelper.md)
    
- [<span data-ttu-id="0c806-124">IOlkAccountManager</span><span class="sxs-lookup"><span data-stu-id="0c806-124">IOlkAccountManager</span></span>](iolkaccountmanager.md)
    
- [<span data-ttu-id="0c806-125">IOlkAccountNotify</span><span class="sxs-lookup"><span data-stu-id="0c806-125">IOlkAccountNotify</span></span>](iolkaccountnotify.md)
    
- [<span data-ttu-id="0c806-126">IOlkEnum</span><span class="sxs-lookup"><span data-stu-id="0c806-126">IOlkEnum</span></span>](iolkenum.md)
    
- [<span data-ttu-id="0c806-127">IOlkErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="0c806-127">IOlkErrorUnknown</span></span>](iolkerrorunknown.md)
    
### <a name="named-properties"></a><span data-ttu-id="0c806-128">命名属性</span><span class="sxs-lookup"><span data-stu-id="0c806-128">Named properties</span></span>
  
- [<span data-ttu-id="0c806-129">PidLidInternetAccountName</span><span class="sxs-lookup"><span data-stu-id="0c806-129">PidLidInternetAccountName</span></span>](pidlidinternetaccountname.md)
    
- [<span data-ttu-id="0c806-130">PidLidInternetAccountStamp</span><span class="sxs-lookup"><span data-stu-id="0c806-130">PidLidInternetAccountStamp</span></span>](pidlidinternetaccountstamp.md)
    
### <a name="properties"></a><span data-ttu-id="0c806-131">属性</span><span class="sxs-lookup"><span data-stu-id="0c806-131">Properties</span></span>
  
- [<span data-ttu-id="0c806-132">PidTagNextSendAcct</span><span class="sxs-lookup"><span data-stu-id="0c806-132">PidTagNextSendAcct</span></span>](pidtagnextsendacct.md)
    
- [<span data-ttu-id="0c806-133">PidTagPrimarySendAccount</span><span class="sxs-lookup"><span data-stu-id="0c806-133">PidTagPrimarySendAccount</span></span>](pidtagprimarysendaccount.md)
    
- [<span data-ttu-id="0c806-134">PROP_ACCT_DELIVERY_FOLDER</span><span class="sxs-lookup"><span data-stu-id="0c806-134">PROP_ACCT_DELIVERY_FOLDER</span></span>](prop_acct_delivery_folder.md)
    
- [<span data-ttu-id="0c806-135">PROP_ACCT_DELIVERY_STORE</span><span class="sxs-lookup"><span data-stu-id="0c806-135">PROP_ACCT_DELIVERY_STORE</span></span>](prop_acct_delivery_store.md)
    
- [<span data-ttu-id="0c806-136">PROP_ACCT_ID</span><span class="sxs-lookup"><span data-stu-id="0c806-136">PROP_ACCT_ID</span></span>](prop_acct_id.md)
    
- [<span data-ttu-id="0c806-137">PROP_ACCT_IS_EXCH</span><span class="sxs-lookup"><span data-stu-id="0c806-137">PROP_ACCT_IS_EXCH</span></span>](prop_acct_is_exch.md)
    
- [<span data-ttu-id="0c806-138">PROP_ACCT_NAME</span><span class="sxs-lookup"><span data-stu-id="0c806-138">PROP_ACCT_NAME</span></span>](prop_acct_name.md)
    
- [<span data-ttu-id="0c806-139">PROP_ACCT_PREFERENCES_UID</span><span class="sxs-lookup"><span data-stu-id="0c806-139">PROP_ACCT_PREFERENCES_UID</span></span>](prop_acct_preferences_uid.md)
    
- [<span data-ttu-id="0c806-140">PROP_ACCT_SEND_STAMP</span><span class="sxs-lookup"><span data-stu-id="0c806-140">PROP_ACCT_SEND_STAMP</span></span>](prop_acct_send_stamp.md)
    
- [<span data-ttu-id="0c806-141">PROP_ACCT_SENTITEMS_EID</span><span class="sxs-lookup"><span data-stu-id="0c806-141">PROP_ACCT_SENTITEMS_EID</span></span>](prop_acct_sentitems_eid.md)
    
- [<span data-ttu-id="0c806-142">PROP_ACCT_STAMP</span><span class="sxs-lookup"><span data-stu-id="0c806-142">PROP_ACCT_STAMP</span></span>](prop_acct_stamp.md)
    
- [<span data-ttu-id="0c806-143">PROP_ACCT_USER_EMAIL_ADDR</span><span class="sxs-lookup"><span data-stu-id="0c806-143">PROP_ACCT_USER_EMAIL_ADDR</span></span>](prop_acct_user_email_addr.md)
    
- [<span data-ttu-id="0c806-144">PROP_ACCT_USER_DISPLAY_NAME</span><span class="sxs-lookup"><span data-stu-id="0c806-144">PROP_ACCT_USER_DISPLAY_NAME</span></span>](prop_acct_user_display_name.md)
    
- [<span data-ttu-id="0c806-145">PROP_MAPI_EMSMDB_UID</span><span class="sxs-lookup"><span data-stu-id="0c806-145">PROP_MAPI_EMSMDB_UID</span></span>](prop_mapi_emsmdb_uid.md)
    
- [<span data-ttu-id="0c806-146">PROP_MAPI_IDENTITY_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="0c806-146">PROP_MAPI_IDENTITY_ENTRYID</span></span>](prop_mapi_identity_entryid.md)
    
- [<span data-ttu-id="0c806-147">PROP_MAPI_TRANSPORT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0c806-147">PROP_MAPI_TRANSPORT_FLAGS</span></span>](prop_mapi_transport_flags.md)
    

