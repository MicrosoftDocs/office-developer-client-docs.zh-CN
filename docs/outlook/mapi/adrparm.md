---
title: ADRPARM
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ADRPARM
api_type:
- COM
ms.assetid: 35cd57b4-9901-456c-bf06-1f84e274eb4e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9663a25a50d914f47cff48124898d16318bbbc43
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425895"
---
# <a name="adrparm"></a><span data-ttu-id="595db-103">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="595db-103">ADRPARM</span></span>

<span data-ttu-id="595db-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="595db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="595db-105">描述常用地址对话框的显示和行为。</span><span class="sxs-lookup"><span data-stu-id="595db-105">Describes the display and behavior of the common address dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="595db-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="595db-106">Header file:</span></span>  <br/> |<span data-ttu-id="595db-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="595db-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _ADRPARM
{
  ULONG cbABContEntryID;
  LPENTRYID lpABContEntryID;
  ULONG ulFlags;
  LPVOID lpReserved;
  ULONG ulHelpContext;
  LPSTR lpszHelpFileName;
  LPFNABSDI lpfnABSDI;
  LPFNDISMISS lpfnDismiss;
  LPVOID lpvDismissContext;
  LPSTR lpszCaption;
  LPSTR lpszNewEntryTitle;
  LPSTR lpszDestWellsTitle;
  ULONG cDestFields;
  ULONG nDestFieldFocus;
  LPSTR FAR *lppszDestTitles;
  ULONG FAR *lpulDestComps;
  LPSRestriction lpContRestriction;
  LPSRestriction lpHierRestriction;
} ADRPARM, FAR *LPADRPARM;

```

## <a name="members"></a><span data-ttu-id="595db-108">Members</span><span class="sxs-lookup"><span data-stu-id="595db-108">Members</span></span>

<span data-ttu-id="595db-109">**cbABContEntryID**</span><span class="sxs-lookup"><span data-stu-id="595db-109">**cbABContEntryID**</span></span>
  
> <span data-ttu-id="595db-110">**lpABContEntryID** 指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="595db-110">Count of bytes in the entry identifier pointed to by **lpABContEntryID**.</span></span>
    
<span data-ttu-id="595db-111">**lpABContEntryID**</span><span class="sxs-lookup"><span data-stu-id="595db-111">**lpABContEntryID**</span></span>
  
> <span data-ttu-id="595db-112">指向容器的条目标识符的指针，该容器提供地址对话框中显示的初始收件人地址列表。</span><span class="sxs-lookup"><span data-stu-id="595db-112">Pointer to the entry identifier of the container that supplies the initial list of recipient addresses that are displayed in the address dialog box.</span></span>
    
<span data-ttu-id="595db-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="595db-113">**ulFlags**</span></span>
  
> <span data-ttu-id="595db-114">与各种地址对话框选项相关联的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="595db-114">Bitmask of flags associated with various address dialog box options.</span></span> <span data-ttu-id="595db-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="595db-115">The following flags can be set:</span></span>
    
<span data-ttu-id="595db-116">AB_RESOLVE</span><span class="sxs-lookup"><span data-stu-id="595db-116">AB_RESOLVE</span></span>
  
> <span data-ttu-id="595db-117">允许在关闭地址对话框后解析所有名称。</span><span class="sxs-lookup"><span data-stu-id="595db-117">Enable all names to be resolved after the address dialog box is closed.</span></span> <span data-ttu-id="595db-118">如果名称解析过程中出现不明确的条目，则会出现一个对话框，提示用户进行解析。</span><span class="sxs-lookup"><span data-stu-id="595db-118">If there are ambiguous entries that result from the name resolution process, a dialog box appears to prompt the user for help in resolving them.</span></span> <span data-ttu-id="595db-119">设置此标志可保证 [IAddrBook：：Address](iaddrbook-address.md) 返回的所有名称已解析。</span><span class="sxs-lookup"><span data-stu-id="595db-119">Setting this flag guarantees that all of the names returned by [IAddrBook::Address](iaddrbook-address.md) are resolved.</span></span> 
    
<span data-ttu-id="595db-120">AB_SELECTONLY</span><span class="sxs-lookup"><span data-stu-id="595db-120">AB_SELECTONLY</span></span>
  
> <span data-ttu-id="595db-121">禁用为收件人列表创建一次地址。</span><span class="sxs-lookup"><span data-stu-id="595db-121">Disable the creation of one-off addresses for a recipient list.</span></span> <span data-ttu-id="595db-122">此标志仅在对话框是模式对话框时使用，如要设置的 DIALOG_MODAL标记所指示。</span><span class="sxs-lookup"><span data-stu-id="595db-122">This flag is used only if the dialog box is modal, as indicated by the DIALOG_MODAL flag being set.</span></span>
    
<span data-ttu-id="595db-123">ADDRESS_ONE</span><span class="sxs-lookup"><span data-stu-id="595db-123">ADDRESS_ONE</span></span>
  
> <span data-ttu-id="595db-124">用户可以仅从列表中选择一个收件人，而不是从列表中选择多个收件人。</span><span class="sxs-lookup"><span data-stu-id="595db-124">The user can select exactly one recipient instead of multiple recipients from a list.</span></span> <span data-ttu-id="595db-125">此标志仅在 **cDestFields** 为零且对话框为模式时有效，如要设置的 DIALOG_MODAL标记所指示。</span><span class="sxs-lookup"><span data-stu-id="595db-125">This flag is valid only when **cDestFields** is zero and the dialog box is modal, as indicated by the DIALOG_MODAL flag being set.</span></span> 
    
<span data-ttu-id="595db-126">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="595db-126">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="595db-127">导致显示常用地址对话框的模式版本。</span><span class="sxs-lookup"><span data-stu-id="595db-127">Causes the modal version of the common address dialog box to be displayed.</span></span> <span data-ttu-id="595db-128">应设置此DIALOG_SDI或值;它们不能同时设置。</span><span class="sxs-lookup"><span data-stu-id="595db-128">Either this flag or DIALOG_SDI should be set; they cannot both be set.</span></span> 
    
<span data-ttu-id="595db-129">DIALOG_OPTIONS</span><span class="sxs-lookup"><span data-stu-id="595db-129">DIALOG_OPTIONS</span></span>
  
> <span data-ttu-id="595db-130">使 **"发送选项** "按钮显示在对话框中。</span><span class="sxs-lookup"><span data-stu-id="595db-130">Causes the **Send Options** button to be displayed in the dialog box.</span></span> <span data-ttu-id="595db-131">此标志仅在对话框是模式对话框时使用，如要设置的 DIALOG_MODAL标记所指示。</span><span class="sxs-lookup"><span data-stu-id="595db-131">This flag is used only if the dialog box is modal, as indicated by the DIALOG_MODAL flag being set.</span></span> 
    
<span data-ttu-id="595db-132">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="595db-132">DIALOG_SDI</span></span>
  
> <span data-ttu-id="595db-133">导致显示公用地址对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="595db-133">Causes the modeless version of the common address dialog box to be displayed.</span></span> <span data-ttu-id="595db-134">应设置此DIALOG_MODAL或值;它们不能同时设置。</span><span class="sxs-lookup"><span data-stu-id="595db-134">Either this flag or DIALOG_MODAL should be set; they cannot both be set.</span></span> <span data-ttu-id="595db-135">对于DIALOG_SDI客户端，将忽略 Outlook 标志，并显示对话框的模式版本。</span><span class="sxs-lookup"><span data-stu-id="595db-135">The DIALOG_SDI flag is ignored for non-Outlook clients, and the modal version of the dialog box will be displayed.</span></span> <span data-ttu-id="595db-136">因此 [，IAddrBook：：Address](iaddrbook-address.md)的 _lpulUIParam_ 参数不应期望指向句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-136">Consequently, a pointer to a handle should not be expected in the  _lpulUIParam_ parameter of [IAddrBook::Address](iaddrbook-address.md).</span></span>
    
<span data-ttu-id="595db-137">**lpReserved**</span><span class="sxs-lookup"><span data-stu-id="595db-137">**lpReserved**</span></span>
  
> <span data-ttu-id="595db-138">保留，必须为零。</span><span class="sxs-lookup"><span data-stu-id="595db-138">Reserved, must be zero.</span></span>
    
<span data-ttu-id="595db-139">**ulHelpContext**</span><span class="sxs-lookup"><span data-stu-id="595db-139">**ulHelpContext**</span></span>
  
> <span data-ttu-id="595db-140">指定当用户单击地址对话框中的"帮助"按钮时将首先显示的"帮助"中的上下文。</span><span class="sxs-lookup"><span data-stu-id="595db-140">Specifies the context within **Help** that will first be shown when the user clicks the Help button in the address dialog box.</span></span> 
    
<span data-ttu-id="595db-141">**lpszHelpFileName**</span><span class="sxs-lookup"><span data-stu-id="595db-141">**lpszHelpFileName**</span></span>
  
> <span data-ttu-id="595db-142">指向将与地址对话框关联的帮助文件的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-142">Pointer to the name of a Help file that will be associated with the address dialog box.</span></span> <span data-ttu-id="595db-143">**lpszHelpFileName** 成员与 **ulHelpContext** 一起用于调用 Windows **WinHelp** 函数。</span><span class="sxs-lookup"><span data-stu-id="595db-143">The **lpszHelpFileName** member is used together with **ulHelpContext** to call the Windows **WinHelp** function.</span></span> 
    
<span data-ttu-id="595db-144">**lpfnABSDI**</span><span class="sxs-lookup"><span data-stu-id="595db-144">**lpfnABSDI**</span></span>
  
> <span data-ttu-id="595db-145">指向基于 [ACCELERATEABSDI](accelerateabsdi.md) 原型或 NULL 的 MAPI 函数的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-145">Pointer to a MAPI function based on the [ACCELERATEABSDI](accelerateabsdi.md) prototype or NULL.</span></span> <span data-ttu-id="595db-146">此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 标志所指示。</span><span class="sxs-lookup"><span data-stu-id="595db-146">This member applies to the modeless version of the dialog box only, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="595db-147">生成要传递到 [IAddrBook：：Address](iaddrbook-address.md) **的 ADRPARM** 结构的客户端必须始终将 **lpfnABSDI** 成员设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="595db-147">Clients building an **ADRPARM** structure to pass to [IAddrBook::Address](iaddrbook-address.md) must always set the **lpfnABSDI** member to NULL.</span></span> <span data-ttu-id="595db-148">如果设置了DIALOG_SDI，MAPI 会先将它设置为有效的函数，然后再返回。</span><span class="sxs-lookup"><span data-stu-id="595db-148">If the DIALOG_SDI flag is set, MAPI will then set it to a valid function before returning.</span></span> <span data-ttu-id="595db-149">客户端在邮件循环中调用此函数，以确保通讯簿对话框中的加速键正常工作。</span><span class="sxs-lookup"><span data-stu-id="595db-149">Clients call this function from in their message loop to make sure that accelerators in the address book dialog box work.</span></span> <span data-ttu-id="595db-150">当对话框关闭并且 MAPI 调用 **lpfnDismiss** 成员指向的函数时，客户端应从消息循环中取消 **HOOKABSDI** 函数。</span><span class="sxs-lookup"><span data-stu-id="595db-150">When the dialog box is dismissed and MAPI calls the function pointed to by the **lpfnDismiss** member, clients should unhook the **ACCELERATEABSDI** function from their message loop.</span></span> 
    
<span data-ttu-id="595db-151">**lpfnDismiss**</span><span class="sxs-lookup"><span data-stu-id="595db-151">**lpfnDismiss**</span></span>
  
> <span data-ttu-id="595db-152">指向基于 [DISMISSMODELESS](dismissmodeless.md) 原型或 NULL 的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-152">Pointer to a function based on the [DISMISSMODELESS](dismissmodeless.md) prototype or NULL.</span></span> <span data-ttu-id="595db-153">此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 指示。</span><span class="sxs-lookup"><span data-stu-id="595db-153">This member applies only to the modeless version of the dialog box only, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="595db-154">当用户关闭无模式地址对话框时，MAPI 将调用 **DISMISSMODELESS** 函数，并通知调用 **IAddrBook：：Address** 的客户端对话框不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="595db-154">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client calling **IAddrBook::Address** that the dialog box is no longer active.</span></span> 
    
<span data-ttu-id="595db-155">**lpvDismissContext**</span><span class="sxs-lookup"><span data-stu-id="595db-155">**lpvDismissContext**</span></span>
  
> <span data-ttu-id="595db-156">指向要传递给 **lpfnDismiss** 成员指向 **的 DISMISSMODELESS** 函数的上下文信息的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-156">Pointer to context information to be passed to the **DISMISSMODELESS** function pointed to by the **lpfnDismiss** member.</span></span> <span data-ttu-id="595db-157">此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 指示。</span><span class="sxs-lookup"><span data-stu-id="595db-157">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> 
    
<span data-ttu-id="595db-158">**lpszCaption**</span><span class="sxs-lookup"><span data-stu-id="595db-158">**lpszCaption**</span></span>
  
> <span data-ttu-id="595db-159">指向要用作常用地址对话框标题的文本的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-159">Pointer to text to be used as the title for the common address dialog box.</span></span>
    
<span data-ttu-id="595db-160">**lpszNewEntryTitle**</span><span class="sxs-lookup"><span data-stu-id="595db-160">**lpszNewEntryTitle**</span></span>
  
> <span data-ttu-id="595db-161">指向要用作调用"新建项"对话框或其他对话框的按钮的按钮标签的文本的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-161">Pointer to text to be used as the button label for the button that invokes either the **New Entry** dialog box or another dialog box.</span></span> 
    
<span data-ttu-id="595db-162">**lpszDestWellsTitle**</span><span class="sxs-lookup"><span data-stu-id="595db-162">**lpszDestWellsTitle**</span></span>
  
> <span data-ttu-id="595db-163">指向要用作收件人文本框控件标题的文本的指针，这些控件可以显示在常用地址对话框的模式版本中。</span><span class="sxs-lookup"><span data-stu-id="595db-163">Pointer to text to be used as a title for the recipient text box controls that can appear in the modal version of the common address dialog box.</span></span> <span data-ttu-id="595db-164">此成员不用于无模式对话框。</span><span class="sxs-lookup"><span data-stu-id="595db-164">This member is not used for modeless dialog boxes.</span></span> 
    
<span data-ttu-id="595db-165">**cDestFields**</span><span class="sxs-lookup"><span data-stu-id="595db-165">**cDestFields**</span></span>
  
> <span data-ttu-id="595db-166">地址对话框模式版本中收件人文本框控件的计数;如果对话框为无模式，则为零。</span><span class="sxs-lookup"><span data-stu-id="595db-166">Count of recipient text box controls in the modal version of the address dialog box, or zero if the dialog box is modeless.</span></span> <span data-ttu-id="595db-167">只有在满足以下条件时，才能打开"地址"对话框进行浏览：</span><span class="sxs-lookup"><span data-stu-id="595db-167">The address dialog box is open for browsing only when the following conditions are true:</span></span> 
    
  - <span data-ttu-id="595db-168">**cDestFields** 成员设置为零。</span><span class="sxs-lookup"><span data-stu-id="595db-168">The **cDestFields** member is set to zero.</span></span> 
    
  - <span data-ttu-id="595db-169">设置DIALOG_BOX标记。</span><span class="sxs-lookup"><span data-stu-id="595db-169">The DIALOG_BOX flag is set.</span></span>
    
  - <span data-ttu-id="595db-170">未ADDRESS_ONE标志。</span><span class="sxs-lookup"><span data-stu-id="595db-170">The ADDRESS_ONE flag is not set.</span></span>
    
  <span data-ttu-id="595db-171">将 **cDestFields** 0XFFFFFFFF表示 MAPI 应创建默认数量的收件人文本框控件。</span><span class="sxs-lookup"><span data-stu-id="595db-171">Setting **cDestFields** to 0XFFFFFFFF implies that MAPI should create the default number of recipient text box controls.</span></span> <span data-ttu-id="595db-172">在这种情况下 **，lppszDestTitles** 和 **lpulDestComps** 成员必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="595db-172">In this case, the **lppszDestTitles** and **lpulDestComps** members must be NULL.</span></span> 
    
<span data-ttu-id="595db-173">**nDestFieldFocus**</span><span class="sxs-lookup"><span data-stu-id="595db-173">**nDestFieldFocus**</span></span>
  
> <span data-ttu-id="595db-174">指示在对话框的模式版本出现时应具有初始焦点的特定文本框控件。</span><span class="sxs-lookup"><span data-stu-id="595db-174">Indicates the particular text box control that should have the initial focus when the modal version of the dialog box appears.</span></span> <span data-ttu-id="595db-175">此值必须介于 0 和 **cDestFields** 的值减 1 之间。</span><span class="sxs-lookup"><span data-stu-id="595db-175">This value must be between 0 and the value of **cDestFields** minus 1.</span></span> 
    
<span data-ttu-id="595db-176">**lppszDestTitles**</span><span class="sxs-lookup"><span data-stu-id="595db-176">**lppszDestTitles**</span></span>
  
> <span data-ttu-id="595db-177">指向与在地址对话框的模式版本中显示的每个文本框控件关联的按钮的标签数组的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-177">Pointer to an array of labels for buttons associated with each of the text box controls that are displayed in the modal version of the address dialog box.</span></span> <span data-ttu-id="595db-178">**cDestFields** 成员的值指示数组中包含的标签数。</span><span class="sxs-lookup"><span data-stu-id="595db-178">The value of the **cDestFields** member indicates the number of labels included in the array.</span></span> <span data-ttu-id="595db-179">如果 **lppszDestTitles** 成员为 NULL， **则 Address** 方法使用默认标题。</span><span class="sxs-lookup"><span data-stu-id="595db-179">If the **lppszDestTitles** member is NULL, the **Address** method uses default titles.</span></span> 
    
<span data-ttu-id="595db-180">**lpulDestComps**</span><span class="sxs-lookup"><span data-stu-id="595db-180">**lpulDestComps**</span></span>
  
> <span data-ttu-id="595db-181">指向与每个文本框控件关联的收件人类型值（如 MAPI_TO、MAPI_CC 和 MAPI_BCC）的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-181">Pointer to an array of recipient type values, such as MAPI_TO, MAPI_CC, and MAPI_BCC, that is associated with each text box control.</span></span> <span data-ttu-id="595db-182">**CDestFields** 成员的值指示数组中包含的收件人类型数。</span><span class="sxs-lookup"><span data-stu-id="595db-182">The value of the **CDestFields** member indicates the number of recipient types included in the array.</span></span> <span data-ttu-id="595db-183">**lpulDestComps** 指向的值可用于将每个收件人的 PR_RECIPIENT_TYPE  ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="595db-183">The values pointed to by **lpulDestComps** can be used to set the **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property of each recipient.</span></span> <span data-ttu-id="595db-184">如果 **lpulDestComps** 成员为 NULL， **则 Address** 方法使用默认收件人类型。</span><span class="sxs-lookup"><span data-stu-id="595db-184">If the **lpulDestComps** member is NULL, the **Address** method uses default recipient types.</span></span> 
    
<span data-ttu-id="595db-185">**lpContRestriction**</span><span class="sxs-lookup"><span data-stu-id="595db-185">**lpContRestriction**</span></span>
  
> <span data-ttu-id="595db-186">指向限制可在对话框中显示的地址条目类型的 [SRestriction](srestriction.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="595db-186">Pointer to an [SRestriction](srestriction.md) structure that limits the type of address entries that can be displayed in the dialog box.</span></span> 
    
<span data-ttu-id="595db-187">**lpHierRestriction**</span><span class="sxs-lookup"><span data-stu-id="595db-187">**lpHierRestriction**</span></span>
  
> <span data-ttu-id="595db-188">指向 **SRestriction** 结构的指针，该结构限制提供要显示在对话框中的地址条目的通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="595db-188">Pointer to an **SRestriction** structure that limits the address book containers that can supply address entries to be displayed in the dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="595db-189">备注</span><span class="sxs-lookup"><span data-stu-id="595db-189">Remarks</span></span>

<span data-ttu-id="595db-190">**客户端和服务提供商使用 ADRPARM** 结构来控制 MAPI 公用地址对话框的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="595db-190">**ADRPARM** structures are used by clients and service providers to control the appearance and behavior of the MAPI common address dialog boxes.</span></span> <span data-ttu-id="595db-191">地址对话框有两种：无模式和模式。</span><span class="sxs-lookup"><span data-stu-id="595db-191">There are two varieties of the address dialog box: modeless and modal.</span></span> <span data-ttu-id="595db-192">**ADRPARM** 结构中的一些成员适用于两个版本的对话框，但有些仅适用于这两个版本之一。</span><span class="sxs-lookup"><span data-stu-id="595db-192">Some of the members in the **ADRPARM** structure apply to both versions of the dialog box, but some only apply to one of the two versions.</span></span> <span data-ttu-id="595db-193">下表将 **ADRPARM** 结构的成员与常用地址对话框的使用关联。</span><span class="sxs-lookup"><span data-stu-id="595db-193">The following table relates the members of an **ADRPARM** structure to their use with the common address dialog boxes.</span></span> 
  
|<span data-ttu-id="595db-194">ADRPARM 成员</span><span class="sxs-lookup"><span data-stu-id="595db-194">ADRPARM member</span></span>|<span data-ttu-id="595db-195">对话框的类型</span><span class="sxs-lookup"><span data-stu-id="595db-195">Type of dialog box</span></span>|
|:-----|:-----|
|<span data-ttu-id="595db-196">**cbABContEntryID** 和 **lpABContEntryID**</span><span class="sxs-lookup"><span data-stu-id="595db-196">**cbABContEntryID** and **lpABContEntryID**</span></span> <br/> |<span data-ttu-id="595db-197">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="595db-197">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="595db-198">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="595db-198">**ulFlags**</span></span> <br/> |<span data-ttu-id="595db-199">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="595db-199">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="595db-200">**lpReserved**</span><span class="sxs-lookup"><span data-stu-id="595db-200">**lpReserved**</span></span> <br/> |<span data-ttu-id="595db-201">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="595db-201">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="595db-202">**ulHelpContext** 和 **lpszHelpFileName**</span><span class="sxs-lookup"><span data-stu-id="595db-202">**ulHelpContext** and **lpszHelpFileName**</span></span> <br/> |<span data-ttu-id="595db-203">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="595db-203">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="595db-204">**lpfnABSDI**</span><span class="sxs-lookup"><span data-stu-id="595db-204">**lpfnABSDI**</span></span> <br/> |<span data-ttu-id="595db-205">Modeless</span><span class="sxs-lookup"><span data-stu-id="595db-205">Modeless</span></span>  <br/> |
|<span data-ttu-id="595db-206">**lpfnDismiss** 和 **lpvDismissContext**</span><span class="sxs-lookup"><span data-stu-id="595db-206">**lpfnDismiss** and **lpvDismissContext**</span></span> <br/> |<span data-ttu-id="595db-207">Modeless</span><span class="sxs-lookup"><span data-stu-id="595db-207">Modeless</span></span>  <br/> |
|<span data-ttu-id="595db-208">**lpszCaption**</span><span class="sxs-lookup"><span data-stu-id="595db-208">**lpszCaption**</span></span> <br/> |<span data-ttu-id="595db-209">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="595db-209">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="595db-210">**lpszNewEntryTitle**</span><span class="sxs-lookup"><span data-stu-id="595db-210">**lpszNewEntryTitle**</span></span> <br/> |<span data-ttu-id="595db-211">Modal</span><span class="sxs-lookup"><span data-stu-id="595db-211">Modal</span></span>  <br/> |
|<span data-ttu-id="595db-212">lpszDestWellsTitle、cDestFields、nDestFieldFocus、lppszDestTitles 和 **lpulDestComps**    </span><span class="sxs-lookup"><span data-stu-id="595db-212">**lpszDestWellsTitle**, **cDestFields**, **nDestFieldFocus**, **lppszDestTitles**, and **lpulDestComps**</span></span> <br/> |<span data-ttu-id="595db-213">Modal</span><span class="sxs-lookup"><span data-stu-id="595db-213">Modal</span></span>  <br/> |
|<span data-ttu-id="595db-214">**lpContRestriction**</span><span class="sxs-lookup"><span data-stu-id="595db-214">**lpContRestriction**</span></span> <br/> |<span data-ttu-id="595db-215">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="595db-215">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="595db-216">**lpHierRestriction**</span><span class="sxs-lookup"><span data-stu-id="595db-216">**lpHierRestriction**</span></span> <br/> |<span data-ttu-id="595db-217">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="595db-217">Modal and modeless</span></span>  <br/> |
   
<span data-ttu-id="595db-218">无模式对话框是一个或多个通讯簿容器中的条目的只读显示。</span><span class="sxs-lookup"><span data-stu-id="595db-218">The modeless dialog box is a read-only display of entries from one or more address book containers.</span></span> <span data-ttu-id="595db-219">该对话框可以显示所选容器的所有条目，或限制为仅与由限制建立的条件匹配的那些条目和容器。</span><span class="sxs-lookup"><span data-stu-id="595db-219">The dialog box can display all entries from the selected containers or be limited to only those entries and containers that match criteria established by a restriction.</span></span> <span data-ttu-id="595db-220">**lpContRestriction** 指向的内容限制可以限制显示的条目类型 **，lpHierRestriction** 指向的层次结构限制可以限制提供条目的容器。</span><span class="sxs-lookup"><span data-stu-id="595db-220">The contents restriction pointed to by **lpContRestriction** can limit the types of entries displayed and the hierarchy restriction pointed to by **lpHierRestriction** can limit the containers providing the entries.</span></span> <span data-ttu-id="595db-221">为了在对话框关闭时通知调用方，MAPI 调用由调用方提供的与 [DISMISSMODELESS](dismissmodeless.md) 原型匹配的函数。</span><span class="sxs-lookup"><span data-stu-id="595db-221">To inform the caller when the dialog box is dismissed, MAPI invokes a function that is provided by the caller that matches the [DISMISSMODELESS](dismissmodeless.md) prototype.</span></span> <span data-ttu-id="595db-222">另一个与[ACCELERATEABSDI](accelerateabsdi.md)原型匹配的函数由 MAPI 提供，由 Windows 消息循环中的调用方调用，以便于键盘快捷方式的运行。</span><span class="sxs-lookup"><span data-stu-id="595db-222">Another function, one that matches the [ACCELERATEABSDI](accelerateabsdi.md) prototype, is provided by MAPI and invoked by the caller in the Windows message loop to facilitate the working of keyboard shortcuts.</span></span> <span data-ttu-id="595db-223">当客户端调用 [IAddrBook：：Address](iaddrbook-address.md) 或服务提供商调用 [IMAPISupport：：Address](imapisupport-address.md)时，可以显示无模式版本的 MAPI 地址对话框。</span><span class="sxs-lookup"><span data-stu-id="595db-223">The modeless version of the MAPI address dialog box can be displayed when clients call [IAddrBook::Address](iaddrbook-address.md) or when service providers call [IMAPISupport::Address](imapisupport-address.md).</span></span> 
  
<span data-ttu-id="595db-224">模式对话框是一个或多个容器中的条目的读/写显示。</span><span class="sxs-lookup"><span data-stu-id="595db-224">The modal dialog box is a read/write display of entries from one or more containers.</span></span> <span data-ttu-id="595db-225">其内容可能会像无模式版本一样受到 **lpContRestriction** 和 **lpHierRestriction** 成员中设置的限制的影响。</span><span class="sxs-lookup"><span data-stu-id="595db-225">Its contents can be affected in the same manner as the modeless version by restrictions set in the **lpContRestriction** and **lpHierRestriction** members.</span></span> <span data-ttu-id="595db-226">除了显示容器项的列表框之外，模式对话框还可以包含一到三个文本框控件，用于保持用户选择的条目。</span><span class="sxs-lookup"><span data-stu-id="595db-226">In addition to the list box displaying container entries, the modal dialog box can contain between one and three text box controls for holding entries selected by the user.</span></span> <span data-ttu-id="595db-227">每个编辑控件都与特定的收件人类型或 **PR_RECIPIENT_TYPE属性（** 如MAPI_TO）。</span><span class="sxs-lookup"><span data-stu-id="595db-227">Each edit control is associated with a particular recipient type or **PR_RECIPIENT_TYPE** property such as MAPI_TO.</span></span> <span data-ttu-id="595db-228">模式地址对话框可以通过任一 **Address** 方法显示，或在客户端调用 [IAddrBook：:D etails](iaddrbook-details.md) 和服务提供商调用 [IMAPISupport：:D etails 时显示](imapisupport-details.md)。</span><span class="sxs-lookup"><span data-stu-id="595db-228">The modal address dialog box can be displayed by either of the **Address** methods or when clients call [IAddrBook::Details](iaddrbook-details.md) and service providers call [IMAPISupport::Details](imapisupport-details.md).</span></span> 
  
<span data-ttu-id="595db-229">此图包含两个文本框控件，因为控制此对话框显示的 **ADRPARM** 结构的 **cDestFields** 成员设置为 2。</span><span class="sxs-lookup"><span data-stu-id="595db-229">This illustration includes two text box controls because the **cDestFields** member of the **ADRPARM** structure controlling the display of this dialog box is set to 2.</span></span> <span data-ttu-id="595db-230">第一个控件具有初始焦点， **因为 nDestFieldFocus** 成员设置为 0。</span><span class="sxs-lookup"><span data-stu-id="595db-230">The first control has initial focus because the **nDestFieldFocus** member is set to 0.</span></span> 
  
<span data-ttu-id="595db-231">**lpszNewEntryTitle** 成员指向按钮标签的文本，当选中该标签时，该成员会导致显示其他对话框。</span><span class="sxs-lookup"><span data-stu-id="595db-231">The **lpszNewEntryTitle** member points to text for a button label that, when it is selected, causes an additional dialog box to be displayed.</span></span> <span data-ttu-id="595db-232">通常，如模式对话框的图示所示，该按钮标记为"新建"，并且出现的对话框列出了配置文件中任何通讯簿提供程序都可以创建的所有地址类型。</span><span class="sxs-lookup"><span data-stu-id="595db-232">Typically, as is shown in the illustration of the modal dialog box, the button is labeled **New** and the dialog box that appears lists all of the types of addresses that can be created by any of the address book providers in the profile.</span></span> <span data-ttu-id="595db-233">客户端 **通过调用**[IAddrBook：：NewEntry，](iaddrbook-newentry.md)为 _cbEidNewEntryTpl_ 参数传递零，在用户选择按钮时为 _lpEidNewEntryTpl_ 参数传递 NULL 来显示此"新建条目"对话框。</span><span class="sxs-lookup"><span data-stu-id="595db-233">Clients cause this **New Entry** dialog box to be displayed by calling [IAddrBook::NewEntry](iaddrbook-newentry.md) and passing zero for the  _cbEidNewEntryTpl_ parameter and NULL for the  _lpEidNewEntryTpl_ parameter when the user selects the button.</span></span> <span data-ttu-id="595db-234">此对话框中包含的信息来自 MAPI 一对一表。</span><span class="sxs-lookup"><span data-stu-id="595db-234">The information that is included in this dialog box comes from the MAPI one-off table.</span></span> 
  
<span data-ttu-id="595db-235">此对话框中的每一项都与模板相关联，模板用于输入创建特定类型地址所需的数据。</span><span class="sxs-lookup"><span data-stu-id="595db-235">Every entry in this dialog box is associated with a template for entering the data required to create an address of the particular type.</span></span> <span data-ttu-id="595db-236">大多数通讯簿提供程序都为可以创建的每种地址条目类型提供一个模板。</span><span class="sxs-lookup"><span data-stu-id="595db-236">Most address book providers supply one template for every type of address entry they can create.</span></span> <span data-ttu-id="595db-237">当用户从此对话框中进行选择时，MAPI 将显示相应的模板。</span><span class="sxs-lookup"><span data-stu-id="595db-237">When a user makes a selection from this dialog box, MAPI displays the corresponding template.</span></span>
  
<span data-ttu-id="595db-238">**ADRPARM** 结构的 **ulFlags** 成员最重要的四位包含标识 **ADRPARM** 结构的版本的版本号。</span><span class="sxs-lookup"><span data-stu-id="595db-238">The most significant four bits of the **ADRPARM** structure's **ulFlags** member contain a version number identifying the version of the **ADRPARM** structure.</span></span> <span data-ttu-id="595db-239">当前版本为 0 (零) 或 ADRPARM_HELP_CTX。</span><span class="sxs-lookup"><span data-stu-id="595db-239">The current version is 0 (zero) or ADRPARM_HELP_CTX.</span></span> <span data-ttu-id="595db-240">MAPI 的当前实现对于除零外的任何版本的结构都将失败。</span><span class="sxs-lookup"><span data-stu-id="595db-240">The current implementation of MAPI will fail for any version of the structure other than zero.</span></span> 
  
<span data-ttu-id="595db-241">结构的未来版本可能完全不同;它们可能不支持零版本结构。</span><span class="sxs-lookup"><span data-stu-id="595db-241">Future versions of the structure may be completely different; they may not support the version-zero structure.</span></span> <span data-ttu-id="595db-242">提供了以下宏，用于从 **ulFlags** 成员中提取版本号以及将版本号与定义标志合并：</span><span class="sxs-lookup"><span data-stu-id="595db-242">The following macros are provided for extracting the version number from the **ulFlags** member and for combining it with the defined flags:</span></span> 
  
- <span data-ttu-id="595db-243">**GET_ADRPARM_VERSION (** _ulFlags)_</span><span class="sxs-lookup"><span data-stu-id="595db-243">**GET_ADRPARM_VERSION** (_ulFlags_)</span></span> 
- <span data-ttu-id="595db-244">**SET_ADRPARM_VERSION (** _ulFlags_， _ ulVersion _) </span><span class="sxs-lookup"><span data-stu-id="595db-244">**SET_ADRPARM_VERSION** (_ulFlags_, _ ulVersion _)</span></span> 
- <span data-ttu-id="595db-245">**ADRPARM_HELP_CTX**</span><span class="sxs-lookup"><span data-stu-id="595db-245">**ADRPARM_HELP_CTX**</span></span>
  
## <a name="see-also"></a><span data-ttu-id="595db-246">另请参阅</span><span class="sxs-lookup"><span data-stu-id="595db-246">See also</span></span>

- [<span data-ttu-id="595db-247">ACCELERATEABSDI</span><span class="sxs-lookup"><span data-stu-id="595db-247">ACCELERATEABSDI</span></span>](accelerateabsdi.md)
- [<span data-ttu-id="595db-248">DISMISSMODELESS</span><span class="sxs-lookup"><span data-stu-id="595db-248">DISMISSMODELESS</span></span>](dismissmodeless.md)
- [<span data-ttu-id="595db-249">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="595db-249">IAddrBook::Address</span></span>](iaddrbook-address.md)
- [<span data-ttu-id="595db-250">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="595db-250">IMAPISupport::Address</span></span>](imapisupport-address.md)
- [<span data-ttu-id="595db-251">SRestriction</span><span class="sxs-lookup"><span data-stu-id="595db-251">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="595db-252">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="595db-252">MAPI Structures</span></span>](mapi-structures.md)

