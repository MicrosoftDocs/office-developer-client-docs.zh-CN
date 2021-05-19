---
title: 关于附加 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 78e2806d-bb6f-cd96-21f1-b7c667c73c33
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fefa77a15cc2b8c72a41b29e6299f159a893cee8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415290"
---
# <a name="about-mapi-additions"></a><span data-ttu-id="19b36-103">关于附加 MAPI</span><span class="sxs-lookup"><span data-stu-id="19b36-103">About MAPI additions</span></span>

<span data-ttu-id="19b36-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="19b36-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="19b36-105">MAPI 添加内容是属于邮件应用程序编程接口 (MAPI) （如数据类型、函数和属性）的 API，以前未作为 MAPI 程序员参考的一部分公开和记录。</span><span class="sxs-lookup"><span data-stu-id="19b36-105">MAPI additions are APIs that belong to Messaging Application Programming Interface (MAPI), such as data types, functions, and properties, that were previously not exposed and documented as part of the MAPI Programmer's Reference.</span></span> <span data-ttu-id="19b36-106">它们包括以下定义和属性。</span><span class="sxs-lookup"><span data-stu-id="19b36-106">They include the following definitions and properties.</span></span>
  
## <a name="constant-definitions"></a><span data-ttu-id="19b36-107">常量定义</span><span class="sxs-lookup"><span data-stu-id="19b36-107">Constant definitions</span></span>

- <span data-ttu-id="19b36-108">**[其他 MAPI 常量](mapi-constants.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-108">**[Additional MAPI Constants](mapi-constants.md)**</span></span>
  
## <a name="data-types"></a><span data-ttu-id="19b36-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="19b36-109">Data types</span></span>

- <span data-ttu-id="19b36-110">**[EXCHANGE_STORE_VERSION_NUM](exchange_store_version_num.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-110">**[EXCHANGE_STORE_VERSION_NUM](exchange_store_version_num.md)**</span></span>
    
- <span data-ttu-id="19b36-111">**[FollowUpStatus](followupstatus.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-111">**[FollowUpStatus](followupstatus.md)**</span></span>
    
- <span data-ttu-id="19b36-112">**[Gender](gender.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-112">**[Gender](gender.md)**</span></span>
    
- <span data-ttu-id="19b36-113">**[OlFlagIcon](olflagicon.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-113">**[OlFlagIcon](olflagicon.md)**</span></span>
    
## <a name="functions"></a><span data-ttu-id="19b36-114">函数</span><span class="sxs-lookup"><span data-stu-id="19b36-114">Functions</span></span>

- <span data-ttu-id="19b36-115">**[FixMAPI](fixmapi.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-115">**[FixMAPI](fixmapi.md)**</span></span>
    
## <a name="properties"></a><span data-ttu-id="19b36-116">属性</span><span class="sxs-lookup"><span data-stu-id="19b36-116">Properties</span></span>

<span data-ttu-id="19b36-117">下列属性通常由 message 对象公开。</span><span class="sxs-lookup"><span data-stu-id="19b36-117">The following properties are generally exposed by message objects.</span></span>
  
- <span data-ttu-id="19b36-118">**[PR_BODY_W](pidtagbody-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-118">**[PR_BODY_W](pidtagbody-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-119">**[PR_CONFLICT_ITEMS](pidtagconflictitems-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-119">**[PR_CONFLICT_ITEMS](pidtagconflictitems-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-120">**[PR_DISPLAY_BCC_W](pidtagdisplaybcc-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-120">**[PR_DISPLAY_BCC_W](pidtagdisplaybcc-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-121">**[PR_DISPLAY_CC_W](pidtagdisplaycc-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-121">**[PR_DISPLAY_CC_W](pidtagdisplaycc-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-122">**[PR_DISPLAY_TO_W](pidtagdisplayto-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-122">**[PR_DISPLAY_TO_W](pidtagdisplayto-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-123">**[PR_FLAG_STATUS](pidtagflagstatus-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-123">**[PR_FLAG_STATUS](pidtagflagstatus-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-124">**[PR_FOLLOWUP_ICON](pidtagfollowupicon-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-124">**[PR_FOLLOWUP_ICON](pidtagfollowupicon-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-125">**[PR_INETMAIL_OVERRIDE_FORMAT](pidtaginternetmailoverrideformat-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-125">**[PR_INETMAIL_OVERRIDE_FORMAT](pidtaginternetmailoverrideformat-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-126">**[PR_MESSAGE_CLASS_W](pidtagmessageclass-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-126">**[PR_MESSAGE_CLASS_W](pidtagmessageclass-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-127">**[PR_MSG_EDITOR_FORMAT](pidtagmessageeditorformat-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-127">**[PR_MSG_EDITOR_FORMAT](pidtagmessageeditorformat-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-128">**[PR_NORMALIZED_SUBJECT_W](pidtagnormalizedsubject-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-128">**[PR_NORMALIZED_SUBJECT_W](pidtagnormalizedsubject-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-129">**[PR_SENDER_ADDRTYPE_W](pidtagsenderaddresstype-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-129">**[PR_SENDER_ADDRTYPE_W](pidtagsenderaddresstype-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-130">**[PR_SENDER_EMAIL_ADDRESS_W](pidtagsenderemailaddress-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-130">**[PR_SENDER_EMAIL_ADDRESS_W](pidtagsenderemailaddress-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-131">**[PR_SENDER_NAME_W](pidtagsendername-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-131">**[PR_SENDER_NAME_W](pidtagsendername-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-132">**[PR_SENT_REPRESENTING_ADDRTYPE_W](pidtagsentrepresentingaddresstype-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-132">**[PR_SENT_REPRESENTING_ADDRTYPE_W](pidtagsentrepresentingaddresstype-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-133">**[PR_SENT_REPRESENTING_EMAIL_ADDRESS_W](pidtagsentrepresentingemailaddress-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-133">**[PR_SENT_REPRESENTING_EMAIL_ADDRESS_W](pidtagsentrepresentingemailaddress-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-134">**[PR_SENT_REPRESENTING_NAME_W](pidtagsentrepresentingname-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-134">**[PR_SENT_REPRESENTING_NAME_W](pidtagsentrepresentingname-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-135">**[PR_SUBJECT_PREFIX_W](pidtagsubjectprefix-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-135">**[PR_SUBJECT_PREFIX_W](pidtagsubjectprefix-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-136">**[PR_SUBJECT_W](pidtagsubject-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-136">**[PR_SUBJECT_W](pidtagsubject-canonical-property.md)**</span></span>
    
<span data-ttu-id="19b36-137">下列属性由通讯簿内容表对象公开。</span><span class="sxs-lookup"><span data-stu-id="19b36-137">The following properties are exposed by address book contents table objects.</span></span>
  
- <span data-ttu-id="19b36-138">**[PR_DISPLAY_TYPE_EX](pidtagdisplaytypeex-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-138">**[PR_DISPLAY_TYPE_EX](pidtagdisplaytypeex-canonical-property.md)**</span></span>
    
<span data-ttu-id="19b36-139">以下属性由通讯簿容器对象公开。</span><span class="sxs-lookup"><span data-stu-id="19b36-139">The following properties are exposed by address book container objects.</span></span>
  
- <span data-ttu-id="19b36-140">**[PR_EMS_AB_SERVER](pidtagemsabserver-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-140">**[PR_EMS_AB_SERVER](pidtagemsabserver-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-141">**[PR_EMS_AB_SERVER_A](pidtagemsabserver-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-141">**[PR_EMS_AB_SERVER_A](pidtagemsabserver-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-142">**[PR_EMS_AB_SERVER_W](pidtagemsabserver-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-142">**[PR_EMS_AB_SERVER_W](pidtagemsabserver-canonical-property.md)**</span></span>
    
<span data-ttu-id="19b36-143">以下属性由文件夹对象公开。</span><span class="sxs-lookup"><span data-stu-id="19b36-143">The following properties are exposed by folder objects.</span></span>
  
- <span data-ttu-id="19b36-144">**[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-144">**[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-145">**[PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-145">**[PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md)**</span></span>
    
<span data-ttu-id="19b36-146">以下属性由邮件用户对象公开。</span><span class="sxs-lookup"><span data-stu-id="19b36-146">The following properties are exposed by messaging user objects.</span></span>
  
- <span data-ttu-id="19b36-147">**[PR_ASSISTANT_TELEPHONE_NUMBER_W](pidtagassistanttelephonenumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-147">**[PR_ASSISTANT_TELEPHONE_NUMBER_W](pidtagassistanttelephonenumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-148">**[PR_ASSISTANT_W](pidtagassistant-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-148">**[PR_ASSISTANT_W](pidtagassistant-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-149">**[PR_ATTACHMENT_CONTACTPHOTO](pidtagattachmentcontactphoto-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-149">**[PR_ATTACHMENT_CONTACTPHOTO](pidtagattachmentcontactphoto-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-150">**[PR_BIRTHDAY](pidtagbirthday-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-150">**[PR_BIRTHDAY](pidtagbirthday-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-151">**[PR_BUSINESS_FAX_NUMBER_W](pidtagbusinessfaxnumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-151">**[PR_BUSINESS_FAX_NUMBER_W](pidtagbusinessfaxnumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-152">**[PR_BUSINESS_HOME_PAGE_W](pidtagbusinesshomepage-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-152">**[PR_BUSINESS_HOME_PAGE_W](pidtagbusinesshomepage-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-153">**[PR_CALLBACK_TELEPHONE_NUMBER_W](pidtagcallbacktelephonenumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-153">**[PR_CALLBACK_TELEPHONE_NUMBER_W](pidtagcallbacktelephonenumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-154">**[PR_CAR_TELEPHONE_NUMBER_W](pidtagcartelephonenumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-154">**[PR_CAR_TELEPHONE_NUMBER_W](pidtagcartelephonenumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-155">**[PR_CELLULAR_TELEPHONE_NUMBER_W](pidtagmobiletelephonenumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-155">**[PR_CELLULAR_TELEPHONE_NUMBER_W](pidtagmobiletelephonenumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-156">**[PR_CHILDRENS_NAMES_W](pidtagchildrensnames-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-156">**[PR_CHILDRENS_NAMES_W](pidtagchildrensnames-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-157">**[PR_DEPARTMENT_NAME_W](pidtagdepartmentname-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-157">**[PR_DEPARTMENT_NAME_W](pidtagdepartmentname-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-158">**[PR_DISPLAY_NAME_PREFIX_W](pidtagdisplaynameprefix-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-158">**[PR_DISPLAY_NAME_PREFIX_W](pidtagdisplaynameprefix-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-159">**[PR_GENDER](pidtaggender-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-159">**[PR_GENDER](pidtaggender-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-160">**[PR_GENERATION_W](pidtaggeneration-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-160">**[PR_GENERATION_W](pidtaggeneration-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-161">**[PR_GIVEN_NAME_W](pidtaggivenname-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-161">**[PR_GIVEN_NAME_W](pidtaggivenname-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-162">**[PR_HOBBIES_W](pidtaghobbies-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-162">**[PR_HOBBIES_W](pidtaghobbies-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-163">**[PR_HOME_ADDRESS_CITY_W](pidtaghomeaddresscity-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-163">**[PR_HOME_ADDRESS_CITY_W](pidtaghomeaddresscity-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-164">**[PR_HOME_ADDRESS_COUNTRY_W](pidtaghomeaddresscountry-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-164">**[PR_HOME_ADDRESS_COUNTRY_W](pidtaghomeaddresscountry-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-165">**[PR_HOME_ADDRESS_POST_OFFICE_BOX_W](pidtaghomeaddresspostofficebox-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-165">**[PR_HOME_ADDRESS_POST_OFFICE_BOX_W](pidtaghomeaddresspostofficebox-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-166">**[PR_HOME_ADDRESS_POSTAL_CODE_W](pidtaghomeaddresspostalcode-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-166">**[PR_HOME_ADDRESS_POSTAL_CODE_W](pidtaghomeaddresspostalcode-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-167">**[PR_HOME_ADDRESS_STATE_OR_PROVINCE_W](pidtaghomeaddressstateorprovince-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-167">**[PR_HOME_ADDRESS_STATE_OR_PROVINCE_W](pidtaghomeaddressstateorprovince-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-168">**[PR_HOME_ADDRESS_STREET_W](pidtaghomeaddressstreet-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-168">**[PR_HOME_ADDRESS_STREET_W](pidtaghomeaddressstreet-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-169">**[PR_HOME_FAX_NUMBER_W](pidtaghomefaxnumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-169">**[PR_HOME_FAX_NUMBER_W](pidtaghomefaxnumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-170">**[PR_HOME_TELEPHONE_NUMBER_W](pidtaghometelephonenumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-170">**[PR_HOME_TELEPHONE_NUMBER_W](pidtaghometelephonenumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-171">**[PR_KEYWORD_W](pidtagkeyword-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-171">**[PR_KEYWORD_W](pidtagkeyword-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-172">**[PR_MANAGER_NAME_W](pidtagmanagername-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-172">**[PR_MANAGER_NAME_W](pidtagmanagername-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-173">**[PR_MIDDLE_NAME_W](pidtagmiddlename-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-173">**[PR_MIDDLE_NAME_W](pidtagmiddlename-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-174">**[PR_NICKNAME_W](pidtagnickname-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-174">**[PR_NICKNAME_W](pidtagnickname-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-175">**[PR_OFFICE_LOCATION_W](pidtagofficelocation-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-175">**[PR_OFFICE_LOCATION_W](pidtagofficelocation-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-176">**[PR_OFFICE_TELEPHONE_NUMBER_W](pidtagbusinesstelephonenumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-176">**[PR_OFFICE_TELEPHONE_NUMBER_W](pidtagbusinesstelephonenumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-177">**[PR_OTHER_ADDRESS_CITY_W](pidtagotheraddresscity-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-177">**[PR_OTHER_ADDRESS_CITY_W](pidtagotheraddresscity-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-178">**[PR_OTHER_ADDRESS_COUNTRY_W](pidtagotheraddresscountry-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-178">**[PR_OTHER_ADDRESS_COUNTRY_W](pidtagotheraddresscountry-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-179">**[PR_OTHER_ADDRESS_POST_OFFICE_BOX_W](pidtagotheraddresspostofficebox-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-179">**[PR_OTHER_ADDRESS_POST_OFFICE_BOX_W](pidtagotheraddresspostofficebox-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-180">**[PR_OTHER_ADDRESS_POSTAL_CODE_W](pidtagotheraddresspostalcode-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-180">**[PR_OTHER_ADDRESS_POSTAL_CODE_W](pidtagotheraddresspostalcode-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-181">**[PR_OTHER_ADDRESS_STATE_OR_PROVINCE_W](pidtagotheraddressstateorprovince-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-181">**[PR_OTHER_ADDRESS_STATE_OR_PROVINCE_W](pidtagotheraddressstateorprovince-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-182">**[PR_OTHER_ADDRESS_STREET_W](pidtagotheraddressstreet-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-182">**[PR_OTHER_ADDRESS_STREET_W](pidtagotheraddressstreet-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-183">**[PR_PAGER_TELEPHONE_NUMBER_W](pidtagpagertelephonenumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-183">**[PR_PAGER_TELEPHONE_NUMBER_W](pidtagpagertelephonenumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-184">**[PR_PERSONAL_HOME_PAGE_W](pidtagpersonalhomepage-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-184">**[PR_PERSONAL_HOME_PAGE_W](pidtagpersonalhomepage-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-185">**[PR_PRIMARY_TELEPHONE_NUMBER_W](pidtagprimarytelephonenumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-185">**[PR_PRIMARY_TELEPHONE_NUMBER_W](pidtagprimarytelephonenumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-186">**[PR_PROFESSION_W](pidtagprofession-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-186">**[PR_PROFESSION_W](pidtagprofession-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-187">**[PR_SPOUSE_NAME_W](pidtagspousename-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-187">**[PR_SPOUSE_NAME_W](pidtagspousename-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-188">**[PR_SURNAME_W](pidtagsurname-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-188">**[PR_SURNAME_W](pidtagsurname-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-189">**[PR_TITLE_W](pidtagtitle-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-189">**[PR_TITLE_W](pidtagtitle-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-190">**[PR_TTYTDD_PHONE_NUMBER_W](pidtagttytddphonenumber-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-190">**[PR_TTYTDD_PHONE_NUMBER_W](pidtagttytddphonenumber-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-191">**[PR_WEDDING_ANNIVERSARY](pidtagweddinganniversary-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-191">**[PR_WEDDING_ANNIVERSARY](pidtagweddinganniversary-canonical-property.md)**</span></span>
    
<span data-ttu-id="19b36-192">以下属性由配置文件节对象公开。</span><span class="sxs-lookup"><span data-stu-id="19b36-192">The following properties are exposed by profile section objects.</span></span>
  
- <span data-ttu-id="19b36-193">**[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-193">**[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-194">**[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-194">**[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-195">**[PR_PROVIDER_DISPLAY_NAME_W](pidtagproviderdisplayname-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-195">**[PR_PROVIDER_DISPLAY_NAME_W](pidtagproviderdisplayname-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-196">**[PR_PROVIDER_ICON_W](pidtagprovidericon-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-196">**[PR_PROVIDER_ICON_W](pidtagprovidericon-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-197">**[PR_ROH_FLAGS](pidtagrpcoverhttpflags-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-197">**[PR_ROH_FLAGS](pidtagrpcoverhttpflags-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-198">**[PR_ROH_PROXY_AUTH_SCHEME](pidtagrpcoverhttpproxyauthscheme-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-198">**[PR_ROH_PROXY_AUTH_SCHEME](pidtagrpcoverhttpproxyauthscheme-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-199">**[PR_ROH_PROXY_PRINCIPAL_NAME](pidtagrpcoverhttpproxyprincipalname-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-199">**[PR_ROH_PROXY_PRINCIPAL_NAME](pidtagrpcoverhttpproxyprincipalname-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-200">**[PR_ROH_PROXY_SERVER](pidtagrpcoverhttpproxyserver-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-200">**[PR_ROH_PROXY_SERVER](pidtagrpcoverhttpproxyserver-canonical-property.md)**</span></span>
    
<span data-ttu-id="19b36-201">以下属性由 store 对象公开。</span><span class="sxs-lookup"><span data-stu-id="19b36-201">The following properties are exposed by store objects.</span></span>
  
- <span data-ttu-id="19b36-202">**[PR_IPM_APPOINTMENT_ENTRYID](pidtagipmappointmententryid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-202">**[PR_IPM_APPOINTMENT_ENTRYID](pidtagipmappointmententryid-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-203">**[PR_IPM_CONTACT_ENTRYID](pidtagipmcontactentryid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-203">**[PR_IPM_CONTACT_ENTRYID](pidtagipmcontactentryid-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-204">**[PR_IPM_DRAFTS_ENTRYID](pidtagipmdraftsentryid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-204">**[PR_IPM_DRAFTS_ENTRYID](pidtagipmdraftsentryid-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-205">**[PR_IPM_JOURNAL_ENTRYID](pidtagipmjournalentryid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-205">**[PR_IPM_JOURNAL_ENTRYID](pidtagipmjournalentryid-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-206">**[PR_IPM_NOTE_ENTRYID](pidtagipmnoteentryid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-206">**[PR_IPM_NOTE_ENTRYID](pidtagipmnoteentryid-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-207">**[PR_IPM_TASK_ENTRYID](pidtagipmtaskentryid-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-207">**[PR_IPM_TASK_ENTRYID](pidtagipmtaskentryid-canonical-property.md)**</span></span>
    
<span data-ttu-id="19b36-208">以下属性由 store 对象公开，用于搜索存储区中电子邮件的特定元素。</span><span class="sxs-lookup"><span data-stu-id="19b36-208">The following properties are exposed by store objects and are used in searching specific elements of an email on the store.</span></span>
  
- <span data-ttu-id="19b36-209">**[PR_SEARCH_ATTACHMENTS_W](pidtagsearchattachments-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-209">**[PR_SEARCH_ATTACHMENTS_W](pidtagsearchattachments-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-210">**[PR_SEARCH_RECIP_EMAIL_BCC_W](pidtagsearchrecipientemailbcc-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-210">**[PR_SEARCH_RECIP_EMAIL_BCC_W](pidtagsearchrecipientemailbcc-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-211">**[PR_SEARCH_RECIP_EMAIL_CC_W](pidtagsearchrecipientemailcc-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-211">**[PR_SEARCH_RECIP_EMAIL_CC_W](pidtagsearchrecipientemailcc-canonical-property.md)**</span></span>
    
- <span data-ttu-id="19b36-212">**[PR_SEARCH_RECIP_EMAIL_TO_W](pidtagsearchrecipientemailto-canonical-property.md)**</span><span class="sxs-lookup"><span data-stu-id="19b36-212">**[PR_SEARCH_RECIP_EMAIL_TO_W](pidtagsearchrecipientemailto-canonical-property.md)**</span></span>
    
## <a name="see-also"></a><span data-ttu-id="19b36-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19b36-213">See also</span></span>

- [<span data-ttu-id="19b36-214">当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="19b36-214">Access a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)  
- [<span data-ttu-id="19b36-215">检测配置文件中Exchange Server的版本Outlook</span><span class="sxs-lookup"><span data-stu-id="19b36-215">Detect the Version of Exchange Server in an Outlook Profile</span></span>](how-to-detect-the-version-of-exchange-server-in-an-outlook-profile.md)
- [<span data-ttu-id="19b36-216">当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="19b36-216">Open a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="19b36-217">在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）</span><span class="sxs-lookup"><span data-stu-id="19b36-217">Manage a Message in an OST Without Invoking a Synchronization in Cached Exchange Mode</span></span>](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

