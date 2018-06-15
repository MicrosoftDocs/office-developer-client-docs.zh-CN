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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ad26cb9b77404d6470f7a8d787eb85edc5cce402
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19774536"
---
# <a name="adrparm"></a><span data-ttu-id="376d8-103">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="376d8-103">ADRPARM</span></span>

<span data-ttu-id="376d8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="376d8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="376d8-105">介绍的显示和行为的通用的地址对话框。</span><span class="sxs-lookup"><span data-stu-id="376d8-105">Describes the display and behavior of the common address dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="376d8-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="376d8-106">Header file:</span></span>  <br/> |<span data-ttu-id="376d8-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="376d8-107">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="376d8-108">成员</span><span class="sxs-lookup"><span data-stu-id="376d8-108">Members</span></span>

<span data-ttu-id="376d8-109">**cbABContEntryID**</span><span class="sxs-lookup"><span data-stu-id="376d8-109">**cbABContEntryID**</span></span>
  
> <span data-ttu-id="376d8-110">由**lpABContEntryID**指向中的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="376d8-110">Count of bytes in the entry identifier pointed to by **lpABContEntryID**.</span></span>
    
<span data-ttu-id="376d8-111">**lpABContEntryID**</span><span class="sxs-lookup"><span data-stu-id="376d8-111">**lpABContEntryID**</span></span>
  
> <span data-ttu-id="376d8-112">提供在地址对话框中显示的收件人地址的初始列表容器的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="376d8-112">Pointer to the entry identifier of the container that supplies the initial list of recipient addresses that are displayed in the address dialog box.</span></span>
    
<span data-ttu-id="376d8-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="376d8-113">**ulFlags**</span></span>
  
> <span data-ttu-id="376d8-114">与各种地址对话框选项相关联标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="376d8-114">Bitmask of flags associated with various address dialog box options.</span></span> <span data-ttu-id="376d8-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="376d8-115">The following flags can be set:</span></span>
    
<span data-ttu-id="376d8-116">AB_RESOLVE</span><span class="sxs-lookup"><span data-stu-id="376d8-116">AB_RESOLVE</span></span>
  
> <span data-ttu-id="376d8-117">启用所有名称解析后关闭地址对话框。</span><span class="sxs-lookup"><span data-stu-id="376d8-117">Enable all names to be resolved after the address dialog box is closed.</span></span> <span data-ttu-id="376d8-118">如果有模糊名称解析过程从结果的条目，将出现一个对话框提示用户输入中解决它们的帮助。</span><span class="sxs-lookup"><span data-stu-id="376d8-118">If there are ambiguous entries that result from the name resolution process, a dialog box appears to prompt the user for help in resolving them.</span></span> <span data-ttu-id="376d8-119">此标志保证所有[IAddrBook::Address](iaddrbook-address.md)返回的名称解析的设置。</span><span class="sxs-lookup"><span data-stu-id="376d8-119">Setting this flag guarantees that all of the names returned by [IAddrBook::Address](iaddrbook-address.md) are resolved.</span></span> 
    
<span data-ttu-id="376d8-120">AB_SELECTONLY</span><span class="sxs-lookup"><span data-stu-id="376d8-120">AB_SELECTONLY</span></span>
  
> <span data-ttu-id="376d8-121">禁用一次性地址的收件人列表的创建。</span><span class="sxs-lookup"><span data-stu-id="376d8-121">Disable the creation of one-off addresses for a recipient list.</span></span> <span data-ttu-id="376d8-122">标志所指示的 DIALOG_MODAL 设置是一个模式对话框，对话框的情况下，才使用此标志。</span><span class="sxs-lookup"><span data-stu-id="376d8-122">This flag is used only if the dialog box is modal, as indicated by the DIALOG_MODAL flag being set.</span></span>
    
<span data-ttu-id="376d8-123">ADDRESS_ONE</span><span class="sxs-lookup"><span data-stu-id="376d8-123">ADDRESS_ONE</span></span>
  
> <span data-ttu-id="376d8-124">用户可以从列表中选择一个收件人，而不是多个收件人。</span><span class="sxs-lookup"><span data-stu-id="376d8-124">The user can select exactly one recipient instead of multiple recipients from a list.</span></span> <span data-ttu-id="376d8-125">仅当**cDestFields**为零，并且对话框是一个模式对话框，如标志所指示的 DIALOG_MODAL 设置时，此标志是有效。</span><span class="sxs-lookup"><span data-stu-id="376d8-125">This flag is valid only when **cDestFields** is zero and the dialog box is modal, as indicated by the DIALOG_MODAL flag being set.</span></span> 
    
<span data-ttu-id="376d8-126">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="376d8-126">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="376d8-127">使通用地址对话框要显示的模式版本。</span><span class="sxs-lookup"><span data-stu-id="376d8-127">Causes the modal version of the common address dialog box to be displayed.</span></span> <span data-ttu-id="376d8-128">此标志或 DIALOG_SDI 应该设置;他们不能同时设置。</span><span class="sxs-lookup"><span data-stu-id="376d8-128">Either this flag or DIALOG_SDI should be set; they cannot both be set.</span></span> 
    
<span data-ttu-id="376d8-129">DIALOG_OPTIONS</span><span class="sxs-lookup"><span data-stu-id="376d8-129">DIALOG_OPTIONS</span></span>
  
> <span data-ttu-id="376d8-130">使**发送选项**按钮，在对话框中显示。</span><span class="sxs-lookup"><span data-stu-id="376d8-130">Causes the **Send Options** button to be displayed in the dialog box.</span></span> <span data-ttu-id="376d8-131">标志所指示的 DIALOG_MODAL 设置是一个模式对话框，对话框的情况下，才使用此标志。</span><span class="sxs-lookup"><span data-stu-id="376d8-131">This flag is used only if the dialog box is modal, as indicated by the DIALOG_MODAL flag being set.</span></span> 
    
<span data-ttu-id="376d8-132">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="376d8-132">DIALOG_SDI</span></span>
  
> <span data-ttu-id="376d8-133">使通用地址对话框要显示的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="376d8-133">Causes the modeless version of the common address dialog box to be displayed.</span></span> <span data-ttu-id="376d8-134">此标志或 DIALOG_MODAL 应该设置;他们不能同时设置。</span><span class="sxs-lookup"><span data-stu-id="376d8-134">Either this flag or DIALOG_MODAL should be set; they cannot both be set.</span></span> <span data-ttu-id="376d8-135">DIALOG_SDI 标志，则忽略非 Outlook 客户端，并将显示模式对话框中的版本。</span><span class="sxs-lookup"><span data-stu-id="376d8-135">The DIALOG_SDI flag is ignored for non-Outlook clients, and the modal version of the dialog box will be displayed.</span></span> <span data-ttu-id="376d8-136">因此，不应[IAddrBook::Address](iaddrbook-address.md)的_lpulUIParam_参数中预期的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="376d8-136">Consequently, a pointer to a handle should not be expected in the  _lpulUIParam_ parameter of [IAddrBook::Address](iaddrbook-address.md).</span></span>
    
<span data-ttu-id="376d8-137">**lpReserved**</span><span class="sxs-lookup"><span data-stu-id="376d8-137">**lpReserved**</span></span>
  
> <span data-ttu-id="376d8-138">保留，必须为零。</span><span class="sxs-lookup"><span data-stu-id="376d8-138">Reserved, must be zero.</span></span>
    
<span data-ttu-id="376d8-139">**ulHelpContext**</span><span class="sxs-lookup"><span data-stu-id="376d8-139">**ulHelpContext**</span></span>
  
> <span data-ttu-id="376d8-140">指定的上下文中**帮助**的将首先显示当用户单击地址对话框中的帮助按钮。</span><span class="sxs-lookup"><span data-stu-id="376d8-140">Specifies the context within **Help** that will first be shown when the user clicks the Help button in the address dialog box.</span></span> 
    
<span data-ttu-id="376d8-141">**lpszHelpFileName**</span><span class="sxs-lookup"><span data-stu-id="376d8-141">**lpszHelpFileName**</span></span>
  
> <span data-ttu-id="376d8-142">指针，指向地址对话框与关联的帮助文件的名称。</span><span class="sxs-lookup"><span data-stu-id="376d8-142">Pointer to the name of a Help file that will be associated with the address dialog box.</span></span> <span data-ttu-id="376d8-143">**LpszHelpFileName**成员一起**ulHelpContext**调用 Windows **WinHelp**函数。</span><span class="sxs-lookup"><span data-stu-id="376d8-143">The **lpszHelpFileName** member is used together with **ulHelpContext** to call the Windows **WinHelp** function.</span></span> 
    
<span data-ttu-id="376d8-144">**lpfnABSDI**</span><span class="sxs-lookup"><span data-stu-id="376d8-144">**lpfnABSDI**</span></span>
  
> <span data-ttu-id="376d8-145">指向 MAPI 函数基于[ACCELERATEABSDI](accelerateabsdi.md)原型或 NULL。</span><span class="sxs-lookup"><span data-stu-id="376d8-145">Pointer to a MAPI function based on the [ACCELERATEABSDI](accelerateabsdi.md) prototype or NULL.</span></span> <span data-ttu-id="376d8-146">此成员适用于无模式对话框中，版如标志所指示的 DIALOG_SDI 设置。</span><span class="sxs-lookup"><span data-stu-id="376d8-146">This member applies to the modeless version of the dialog box only, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="376d8-147">构建要传递给[IAddrBook::Address](iaddrbook-address.md) **ADRPARM**结构的客户端必须始终设置为 NULL 的**lpfnABSDI**成员。</span><span class="sxs-lookup"><span data-stu-id="376d8-147">Clients building an **ADRPARM** structure to pass to [IAddrBook::Address](iaddrbook-address.md) must always set the **lpfnABSDI** member to NULL.</span></span> <span data-ttu-id="376d8-148">如果设置了 DIALOG_SDI 标志，MAPI 将然后将其设置为有效的函数返回之前。</span><span class="sxs-lookup"><span data-stu-id="376d8-148">If the DIALOG_SDI flag is set, MAPI will then set it to a valid function before returning.</span></span> <span data-ttu-id="376d8-149">客户端调用该函数从其邮件循环，以确保地址中的加速键书籍对话框框工作。</span><span class="sxs-lookup"><span data-stu-id="376d8-149">Clients call this function from in their message loop to make sure that accelerators in the address book dialog box work.</span></span> <span data-ttu-id="376d8-150">当被关闭对话框并 MAPI 调用指向**lpfnDismiss**成员的函数时，客户端应断开**ACCELERATEABSDI**函数从其消息循环。</span><span class="sxs-lookup"><span data-stu-id="376d8-150">When the dialog box is dismissed and MAPI calls the function pointed to by the **lpfnDismiss** member, clients should unhook the **ACCELERATEABSDI** function from their message loop.</span></span> 
    
<span data-ttu-id="376d8-151">**lpfnDismiss**</span><span class="sxs-lookup"><span data-stu-id="376d8-151">**lpfnDismiss**</span></span>
  
> <span data-ttu-id="376d8-152">指向函数基于[DISMISSMODELESS](dismissmodeless.md)原型或 NULL。</span><span class="sxs-lookup"><span data-stu-id="376d8-152">Pointer to a function based on the [DISMISSMODELESS](dismissmodeless.md) prototype or NULL.</span></span> <span data-ttu-id="376d8-153">此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。</span><span class="sxs-lookup"><span data-stu-id="376d8-153">This member applies only to the modeless version of the dialog box only, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="376d8-154">MAPI 调用的**DISMISSMODELESS**函数时在用户关闭无模式的地址对话框，通知调用**IAddrBook::Address**对话框中不再处于活动状态的客户端。</span><span class="sxs-lookup"><span data-stu-id="376d8-154">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client calling **IAddrBook::Address** that the dialog box is no longer active.</span></span> 
    
<span data-ttu-id="376d8-155">**lpvDismissContext**</span><span class="sxs-lookup"><span data-stu-id="376d8-155">**lpvDismissContext**</span></span>
  
> <span data-ttu-id="376d8-156">指向上下文信息传递给**DISMISSMODELESS**函数指针指向由**lpfnDismiss**成员。</span><span class="sxs-lookup"><span data-stu-id="376d8-156">Pointer to context information to be passed to the **DISMISSMODELESS** function pointed to by the **lpfnDismiss** member.</span></span> <span data-ttu-id="376d8-157">此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。</span><span class="sxs-lookup"><span data-stu-id="376d8-157">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> 
    
<span data-ttu-id="376d8-158">**lpszCaption**</span><span class="sxs-lookup"><span data-stu-id="376d8-158">**lpszCaption**</span></span>
  
> <span data-ttu-id="376d8-159">指向要用作通用的地址对话框标题文本。</span><span class="sxs-lookup"><span data-stu-id="376d8-159">Pointer to text to be used as the title for the common address dialog box.</span></span>
    
<span data-ttu-id="376d8-160">**lpszNewEntryTitle**</span><span class="sxs-lookup"><span data-stu-id="376d8-160">**lpszNewEntryTitle**</span></span>
  
> <span data-ttu-id="376d8-161">指向要用作调用**新项**对话框或另一个对话框中按钮的按钮标签的文本。</span><span class="sxs-lookup"><span data-stu-id="376d8-161">Pointer to text to be used as the button label for the button that invokes either the **New Entry** dialog box or another dialog box.</span></span> 
    
<span data-ttu-id="376d8-162">**lpszDestWellsTitle**</span><span class="sxs-lookup"><span data-stu-id="376d8-162">**lpszDestWellsTitle**</span></span>
  
> <span data-ttu-id="376d8-163">指向要用作收件人文本框控件可以显示模式版本的通用的地址对话框中的标题文本。</span><span class="sxs-lookup"><span data-stu-id="376d8-163">Pointer to text to be used as a title for the recipient text box controls that can appear in the modal version of the common address dialog box.</span></span> <span data-ttu-id="376d8-164">此成员不用于无模式对话框。</span><span class="sxs-lookup"><span data-stu-id="376d8-164">This member is not used for modeless dialog boxes.</span></span> 
    
<span data-ttu-id="376d8-165">**cDestFields**</span><span class="sxs-lookup"><span data-stu-id="376d8-165">**cDestFields**</span></span>
  
> <span data-ttu-id="376d8-166">在地址对话框中或零，如果无模式对话框模式版本收件人文本框控件的计数。</span><span class="sxs-lookup"><span data-stu-id="376d8-166">Count of recipient text box controls in the modal version of the address dialog box, or zero if the dialog box is modeless.</span></span> <span data-ttu-id="376d8-167">地址对话框中处于打开状态以浏览仅当满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="376d8-167">The address dialog box is open for browsing only when the following conditions are true:</span></span> 
    
  - <span data-ttu-id="376d8-168">**CDestFields**成员设置为零。</span><span class="sxs-lookup"><span data-stu-id="376d8-168">The **cDestFields** member is set to zero.</span></span> 
    
  - <span data-ttu-id="376d8-169">设置 DIALOG_BOX 标志。</span><span class="sxs-lookup"><span data-stu-id="376d8-169">The DIALOG_BOX flag is set.</span></span>
    
  - <span data-ttu-id="376d8-170">未设置 ADDRESS_ONE 标志。</span><span class="sxs-lookup"><span data-stu-id="376d8-170">The ADDRESS_ONE flag is not set.</span></span>
    
  <span data-ttu-id="376d8-171">设置为 0XFFFFFFFF **cDestFields**意味着框控件 MAPI 应创建收件人的文本的默认数。</span><span class="sxs-lookup"><span data-stu-id="376d8-171">Setting **cDestFields** to 0XFFFFFFFF implies that MAPI should create the default number of recipient text box controls.</span></span> <span data-ttu-id="376d8-172">在这种情况下的**lppszDestTitles**和**lpulDestComps**成员必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="376d8-172">In this case, the **lppszDestTitles** and **lpulDestComps** members must be NULL.</span></span> 
    
<span data-ttu-id="376d8-173">**nDestFieldFocus**</span><span class="sxs-lookup"><span data-stu-id="376d8-173">**nDestFieldFocus**</span></span>
  
> <span data-ttu-id="376d8-174">指示特定文本框控件显示的对话框中的模式版本时，应具有的初始焦点。</span><span class="sxs-lookup"><span data-stu-id="376d8-174">Indicates the particular text box control that should have the initial focus when the modal version of the dialog box appears.</span></span> <span data-ttu-id="376d8-175">该值必须介于 0 和**cDestFields**减 1 之间的值之间。</span><span class="sxs-lookup"><span data-stu-id="376d8-175">This value must be between 0 and the value of **cDestFields** minus 1.</span></span> 
    
<span data-ttu-id="376d8-176">**lppszDestTitles**</span><span class="sxs-lookup"><span data-stu-id="376d8-176">**lppszDestTitles**</span></span>
  
> <span data-ttu-id="376d8-177">指向与每个文本框控件的显示模式版本中的地址对话框的按钮标签的数组。</span><span class="sxs-lookup"><span data-stu-id="376d8-177">Pointer to an array of labels for buttons associated with each of the text box controls that are displayed in the modal version of the address dialog box.</span></span> <span data-ttu-id="376d8-178">**CDestFields**成员的值指示数组中包含的标签的数目。</span><span class="sxs-lookup"><span data-stu-id="376d8-178">The value of the **cDestFields** member indicates the number of labels included in the array.</span></span> <span data-ttu-id="376d8-179">如果**lppszDestTitles**成员为 NULL，则该**地址**方法将使用默认标题。</span><span class="sxs-lookup"><span data-stu-id="376d8-179">If the **lppszDestTitles** member is NULL, the **Address** method uses default titles.</span></span> 
    
<span data-ttu-id="376d8-180">**lpulDestComps**</span><span class="sxs-lookup"><span data-stu-id="376d8-180">**lpulDestComps**</span></span>
  
> <span data-ttu-id="376d8-181">指向数组的收件人类型值，如 MAPI_TO、 MAPI_CC 和 MAPI_BCC，这是与每个文本框控件相关联。</span><span class="sxs-lookup"><span data-stu-id="376d8-181">Pointer to an array of recipient type values, such as MAPI_TO, MAPI_CC, and MAPI_BCC, that is associated with each text box control.</span></span> <span data-ttu-id="376d8-182">**CDestFields**成员的值指示的数组中包含的收件人类型的数目。</span><span class="sxs-lookup"><span data-stu-id="376d8-182">The value of the **CDestFields** member indicates the number of recipient types included in the array.</span></span> <span data-ttu-id="376d8-183">用于将每个收件人的**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性设置所指的**lpulDestComps**的值。</span><span class="sxs-lookup"><span data-stu-id="376d8-183">The values pointed to by **lpulDestComps** can be used to set the **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property of each recipient.</span></span> <span data-ttu-id="376d8-184">如果**lpulDestComps**成员为 NULL，则该**地址**方法将使用默认的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="376d8-184">If the **lpulDestComps** member is NULL, the **Address** method uses default recipient types.</span></span> 
    
<span data-ttu-id="376d8-185">**lpContRestriction**</span><span class="sxs-lookup"><span data-stu-id="376d8-185">**lpContRestriction**</span></span>
  
> <span data-ttu-id="376d8-186">指向[SRestriction](srestriction.md)结构限制可在对话框中显示的地址条目的类型。</span><span class="sxs-lookup"><span data-stu-id="376d8-186">Pointer to an [SRestriction](srestriction.md) structure that limits the type of address entries that can be displayed in the dialog box.</span></span> 
    
<span data-ttu-id="376d8-187">**lpHierRestriction**</span><span class="sxs-lookup"><span data-stu-id="376d8-187">**lpHierRestriction**</span></span>
  
> <span data-ttu-id="376d8-188">指向限制可以提供要显示在对话框中的地址条目的地址簿容器**SRestriction**结构。</span><span class="sxs-lookup"><span data-stu-id="376d8-188">Pointer to an **SRestriction** structure that limits the address book containers that can supply address entries to be displayed in the dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="376d8-189">备注</span><span class="sxs-lookup"><span data-stu-id="376d8-189">Remarks</span></span>

<span data-ttu-id="376d8-190">由客户端和服务提供商使用的**ADRPARM**结构用于控制的外观和行为的 MAPI 通用地址对话框。</span><span class="sxs-lookup"><span data-stu-id="376d8-190">**ADRPARM** structures are used by clients and service providers to control the appearance and behavior of the MAPI common address dialog boxes.</span></span> <span data-ttu-id="376d8-191">有两种类型的地址对话框： 无模式和模式。</span><span class="sxs-lookup"><span data-stu-id="376d8-191">There are two varieties of the address dialog box: modeless and modal.</span></span> <span data-ttu-id="376d8-192">一些**ADRPARM**结构中的成员将应用于两个版本的对话框中，但某些仅适用于两个版本之一。</span><span class="sxs-lookup"><span data-stu-id="376d8-192">Some of the members in the **ADRPARM** structure apply to both versions of the dialog box, but some only apply to one of the two versions.</span></span> <span data-ttu-id="376d8-193">下表在其使用通用的地址对话框中与**ADRPARM**结构的成员。</span><span class="sxs-lookup"><span data-stu-id="376d8-193">The following table relates the members of an **ADRPARM** structure to their use with the common address dialog boxes.</span></span> 
  
|<span data-ttu-id="376d8-194">ADRPARM 成员</span><span class="sxs-lookup"><span data-stu-id="376d8-194">ADRPARM member</span></span>|<span data-ttu-id="376d8-195">对话框类型</span><span class="sxs-lookup"><span data-stu-id="376d8-195">Type of dialog box</span></span>|
|:-----|:-----|
|<span data-ttu-id="376d8-196">**cbABContEntryID**和**lpABContEntryID**</span><span class="sxs-lookup"><span data-stu-id="376d8-196">**cbABContEntryID** and **lpABContEntryID**</span></span> <br/> |<span data-ttu-id="376d8-197">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="376d8-197">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="376d8-198">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="376d8-198">**ulFlags**</span></span> <br/> |<span data-ttu-id="376d8-199">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="376d8-199">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="376d8-200">**lpReserved**</span><span class="sxs-lookup"><span data-stu-id="376d8-200">**lpReserved**</span></span> <br/> |<span data-ttu-id="376d8-201">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="376d8-201">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="376d8-202">**ulHelpContext**和**lpszHelpFileName**</span><span class="sxs-lookup"><span data-stu-id="376d8-202">**ulHelpContext** and **lpszHelpFileName**</span></span> <br/> |<span data-ttu-id="376d8-203">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="376d8-203">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="376d8-204">**lpfnABSDI**</span><span class="sxs-lookup"><span data-stu-id="376d8-204">**lpfnABSDI**</span></span> <br/> |<span data-ttu-id="376d8-205">无模式</span><span class="sxs-lookup"><span data-stu-id="376d8-205">Modeless</span></span>  <br/> |
|<span data-ttu-id="376d8-206">**lpfnDismiss**和**lpvDismissContext**</span><span class="sxs-lookup"><span data-stu-id="376d8-206">**lpfnDismiss** and **lpvDismissContext**</span></span> <br/> |<span data-ttu-id="376d8-207">无模式</span><span class="sxs-lookup"><span data-stu-id="376d8-207">Modeless</span></span>  <br/> |
|<span data-ttu-id="376d8-208">**lpszCaption**</span><span class="sxs-lookup"><span data-stu-id="376d8-208">**lpszCaption**</span></span> <br/> |<span data-ttu-id="376d8-209">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="376d8-209">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="376d8-210">**lpszNewEntryTitle**</span><span class="sxs-lookup"><span data-stu-id="376d8-210">**lpszNewEntryTitle**</span></span> <br/> |<span data-ttu-id="376d8-211">模式</span><span class="sxs-lookup"><span data-stu-id="376d8-211">Modal</span></span>  <br/> |
|<span data-ttu-id="376d8-212">**lpszDestWellsTitle**、 **cDestFields**、 **nDestFieldFocus**、 **lppszDestTitles**和**lpulDestComps**</span><span class="sxs-lookup"><span data-stu-id="376d8-212">**lpszDestWellsTitle**, **cDestFields**, **nDestFieldFocus**, **lppszDestTitles**, and **lpulDestComps**</span></span> <br/> |<span data-ttu-id="376d8-213">模式</span><span class="sxs-lookup"><span data-stu-id="376d8-213">Modal</span></span>  <br/> |
|<span data-ttu-id="376d8-214">**lpContRestriction**</span><span class="sxs-lookup"><span data-stu-id="376d8-214">**lpContRestriction**</span></span> <br/> |<span data-ttu-id="376d8-215">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="376d8-215">Modal and modeless</span></span>  <br/> |
|<span data-ttu-id="376d8-216">**lpHierRestriction**</span><span class="sxs-lookup"><span data-stu-id="376d8-216">**lpHierRestriction**</span></span> <br/> |<span data-ttu-id="376d8-217">模式和无模式</span><span class="sxs-lookup"><span data-stu-id="376d8-217">Modal and modeless</span></span>  <br/> |
   
<span data-ttu-id="376d8-218">无模式对话框是只读的显示的一个或多个地址簿容器中的条目。</span><span class="sxs-lookup"><span data-stu-id="376d8-218">The modeless dialog box is a read-only display of entries from one or more address book containers.</span></span> <span data-ttu-id="376d8-219">对话框可显示所选的容器中的所有项或被限制为只有那些条目和匹配建立限制条件的容器。</span><span class="sxs-lookup"><span data-stu-id="376d8-219">The dialog box can display all entries from the selected containers or be limited to only those entries and containers that match criteria established by a restriction.</span></span> <span data-ttu-id="376d8-220">所指的**lpContRestriction**内容限制可以限制的显示条目类型并由**lpHierRestriction**指向的层次结构限制可以限制提供条目的容器。</span><span class="sxs-lookup"><span data-stu-id="376d8-220">The contents restriction pointed to by **lpContRestriction** can limit the types of entries displayed and the hierarchy restriction pointed to by **lpHierRestriction** can limit the containers providing the entries.</span></span> <span data-ttu-id="376d8-221">若要向呼叫者时消除对话框中，MAPI，请调用匹配[DISMISSMODELESS](dismissmodeless.md)原型呼叫者提供的函数。</span><span class="sxs-lookup"><span data-stu-id="376d8-221">To inform the caller when the dialog box is dismissed, MAPI invokes a function that is provided by the caller that matches the [DISMISSMODELESS](dismissmodeless.md) prototype.</span></span> <span data-ttu-id="376d8-222">另一个函数，一个匹配[ACCELERATEABSDI](accelerateabsdi.md)原型，是供稿 MAPI，调用 Windows 邮件循环中呼叫者，为了方便的键盘快捷方式工作。</span><span class="sxs-lookup"><span data-stu-id="376d8-222">Another function, one that matches the [ACCELERATEABSDI](accelerateabsdi.md) prototype, is provided by MAPI and invoked by the caller in the Windows message loop to facilitate the working of keyboard shortcuts.</span></span> <span data-ttu-id="376d8-223">客户端调用[IAddrBook::Address](iaddrbook-address.md)时或服务提供商调用[IMAPISupport::Address](imapisupport-address.md)时，可以显示 MAPI 地址对话框中的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="376d8-223">The modeless version of the MAPI address dialog box can be displayed when clients call [IAddrBook::Address](iaddrbook-address.md) or when service providers call [IMAPISupport::Address](imapisupport-address.md).</span></span> 
  
<span data-ttu-id="376d8-224">模式对话框显示的一个或多个容器中的条目的读/写。</span><span class="sxs-lookup"><span data-stu-id="376d8-224">The modal dialog box is a read/write display of entries from one or more containers.</span></span> <span data-ttu-id="376d8-225">其内容会受到影响相同的方式，如成员**lpContRestriction**和**lpHierRestriction**中设置的限制的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="376d8-225">Its contents can be affected in the same manner as the modeless version by restrictions set in the **lpContRestriction** and **lpHierRestriction** members.</span></span> <span data-ttu-id="376d8-226">显示容器条目的列表中，除了模式对话框可以包含一到三个文本框控件的容纳用户所选的项。</span><span class="sxs-lookup"><span data-stu-id="376d8-226">In addition to the list box displaying container entries, the modal dialog box can contain between one and three text box controls for holding entries selected by the user.</span></span> <span data-ttu-id="376d8-227">每个编辑控件相关联的特定收件人类型或如 MAPI_TO **PR_RECIPIENT_TYPE**属性。</span><span class="sxs-lookup"><span data-stu-id="376d8-227">Each edit control is associated with a particular recipient type or **PR_RECIPIENT_TYPE** property such as MAPI_TO.</span></span> <span data-ttu-id="376d8-228">客户端调用[IAddrBook::Details](iaddrbook-details.md)和服务提供商呼叫[IMAPISupport::Details](imapisupport-details.md)时，可以按的**地址**方法或显示模式的地址对话框。</span><span class="sxs-lookup"><span data-stu-id="376d8-228">The modal address dialog box can be displayed by either of the **Address** methods or when clients call [IAddrBook::Details](iaddrbook-details.md) and service providers call [IMAPISupport::Details](imapisupport-details.md).</span></span> 
  
<span data-ttu-id="376d8-229">此图中包括两个文本框控件，因为控制的此对话框中显示的**ADRPARM**结构的**cDestFields**成员设置为 2。</span><span class="sxs-lookup"><span data-stu-id="376d8-229">This illustration includes two text box controls because the **cDestFields** member of the **ADRPARM** structure controlling the display of this dialog box is set to 2.</span></span> <span data-ttu-id="376d8-230">第一个控件具有初始焦点，因为**nDestFieldFocus**成员设置为 0。</span><span class="sxs-lookup"><span data-stu-id="376d8-230">The first control has initial focus because the **nDestFieldFocus** member is set to 0.</span></span> 
  
<span data-ttu-id="376d8-231">**LpszNewEntryTitle**成员指向选中后，将导致附加的对话框中显示的按钮标签的文本。</span><span class="sxs-lookup"><span data-stu-id="376d8-231">The **lpszNewEntryTitle** member points to text for a button label that, when it is selected, causes an additional dialog box to be displayed.</span></span> <span data-ttu-id="376d8-232">通常情况下，如下图所示的模式对话框，该按钮标记为**新建**和出现的对话框中列出的所有通讯簿提供程序配置文件中的任一可以创建的地址类型。</span><span class="sxs-lookup"><span data-stu-id="376d8-232">Typically, as is shown in the illustration of the modal dialog box, the button is labeled **New** and the dialog box that appears lists all of the types of addresses that can be created by any of the address book providers in the profile.</span></span> <span data-ttu-id="376d8-233">客户端导致通过调用[IAddrBook::NewEntry](iaddrbook-newentry.md)和传递零_cbEidNewEntryTpl_参数和_lpEidNewEntryTpl_参数为空，用户选择按钮时显示此**新项**对话框。</span><span class="sxs-lookup"><span data-stu-id="376d8-233">Clients cause this **New Entry** dialog box to be displayed by calling [IAddrBook::NewEntry](iaddrbook-newentry.md) and passing zero for the  _cbEidNewEntryTpl_ parameter and NULL for the  _lpEidNewEntryTpl_ parameter when the user selects the button.</span></span> <span data-ttu-id="376d8-234">在此对话框中包含的信息将来自 MAPI 一次性表。</span><span class="sxs-lookup"><span data-stu-id="376d8-234">The information that is included in this dialog box comes from the MAPI one-off table.</span></span> 
  
<span data-ttu-id="376d8-235">在此对话框中的每个条目都与输入要创建特定类型的地址所需的数据的模板关联。</span><span class="sxs-lookup"><span data-stu-id="376d8-235">Every entry in this dialog box is associated with a template for entering the data required to create an address of the particular type.</span></span> <span data-ttu-id="376d8-236">大多数通讯簿提供程序提供每种类型的地址条目，他们可以创建一个的模板。</span><span class="sxs-lookup"><span data-stu-id="376d8-236">Most address book providers supply one template for every type of address entry they can create.</span></span> <span data-ttu-id="376d8-237">当用户从该对话框中进行选择时，MAPI 显示相应的模板。</span><span class="sxs-lookup"><span data-stu-id="376d8-237">When a user makes a selection from this dialog box, MAPI displays the corresponding template.</span></span>
  
<span data-ttu-id="376d8-238">**ADRPARM**结构的**ulFlags**成员的最重要的四个字节包含标识**ADRPARM**结构的版本的版本号。</span><span class="sxs-lookup"><span data-stu-id="376d8-238">The most significant four bits of the **ADRPARM** structure's **ulFlags** member contain a version number identifying the version of the **ADRPARM** structure.</span></span> <span data-ttu-id="376d8-239">当前版本是 0 （零） 或 ADRPARM_HELP_CTX。</span><span class="sxs-lookup"><span data-stu-id="376d8-239">The current version is 0 (zero) or ADRPARM_HELP_CTX.</span></span> <span data-ttu-id="376d8-240">当前的 MAPI 实现将失败的任何版本的非零的结构。</span><span class="sxs-lookup"><span data-stu-id="376d8-240">The current implementation of MAPI will fail for any version of the structure other than zero.</span></span> 
  
<span data-ttu-id="376d8-241">结构的未来版本可能完全不同;他们可能不支持的版本零结构。</span><span class="sxs-lookup"><span data-stu-id="376d8-241">Future versions of the structure may be completely different; they may not support the version-zero structure.</span></span> <span data-ttu-id="376d8-242">下面的宏提供从**ulFlags**成员中提取的版本号和将它与定义的标志组合：</span><span class="sxs-lookup"><span data-stu-id="376d8-242">The following macros are provided for extracting the version number from the **ulFlags** member and for combining it with the defined flags:</span></span> 
  
- <span data-ttu-id="376d8-243">**GET_ADRPARM_VERSION**(_ulFlags_)</span><span class="sxs-lookup"><span data-stu-id="376d8-243">**GET_ADRPARM_VERSION** (_ulFlags_)</span></span> 
- <span data-ttu-id="376d8-244">**SET_ADRPARM_VERSION**(_ulFlags_，_ ulVersion _)</span><span class="sxs-lookup"><span data-stu-id="376d8-244">**SET_ADRPARM_VERSION** (_ulFlags_, _ ulVersion _)</span></span> 
- <span data-ttu-id="376d8-245">**ADRPARM_HELP_CTX**</span><span class="sxs-lookup"><span data-stu-id="376d8-245">**ADRPARM_HELP_CTX**</span></span>
  
## <a name="see-also"></a><span data-ttu-id="376d8-246">另请参阅</span><span class="sxs-lookup"><span data-stu-id="376d8-246">See also</span></span>

- [<span data-ttu-id="376d8-247">ACCELERATEABSDI</span><span class="sxs-lookup"><span data-stu-id="376d8-247">ACCELERATEABSDI</span></span>](accelerateabsdi.md)
- [<span data-ttu-id="376d8-248">DISMISSMODELESS</span><span class="sxs-lookup"><span data-stu-id="376d8-248">DISMISSMODELESS</span></span>](dismissmodeless.md)
- [<span data-ttu-id="376d8-249">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="376d8-249">IAddrBook::Address</span></span>](iaddrbook-address.md)
- [<span data-ttu-id="376d8-250">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="376d8-250">IMAPISupport::Address</span></span>](imapisupport-address.md)
- [<span data-ttu-id="376d8-251">SRestriction</span><span class="sxs-lookup"><span data-stu-id="376d8-251">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="376d8-252">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="376d8-252">MAPI Structures</span></span>](mapi-structures.md)

