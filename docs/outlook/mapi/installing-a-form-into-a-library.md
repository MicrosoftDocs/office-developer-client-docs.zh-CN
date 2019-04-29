---
title: 将表单安装到库中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 303c9dcb-f9b5-4cea-b5f2-3eba01aa3b09
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 08470a80153e42136922ae502252d83de0125512
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433141"
---
# <a name="installing-a-form-into-a-library"></a><span data-ttu-id="2319b-103">将表单安装到库中</span><span class="sxs-lookup"><span data-stu-id="2319b-103">Installing a Form into a Library</span></span>

  
  
<span data-ttu-id="2319b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2319b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2319b-105">Windows SDK 附带的默认 MAPI 表单管理器不提供用于在各种表单库中安装表单的用户界面。</span><span class="sxs-lookup"><span data-stu-id="2319b-105">The default MAPI form manager supplied with the Windows SDK does not provide a user interface for installing forms in the various form libraries.</span></span> <span data-ttu-id="2319b-106">因此, 您必须创建一个小型应用程序 (或详细的说明集), 以便用户可以使用它来安装表单。</span><span class="sxs-lookup"><span data-stu-id="2319b-106">Because of this, you will have to create a small application — or detailed set of instructions — that users can use to install the form.</span></span>
  
<span data-ttu-id="2319b-107">如果实现安装应用程序, 则必须执行的一系列操作将表单安装到文件夹的关联内容表中, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="2319b-107">If you implement an installation application, the series of actions it must perform to install a form into a folder's associated contents table are as follows:</span></span>
  
1. <span data-ttu-id="2319b-108">调用[MAPIOpenFormMgr](mapiopenformmgr.md)函数以打开窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="2319b-108">Call the [MAPIOpenFormMgr](mapiopenformmgr.md) function to open the form manager.</span></span> 
    
2. <span data-ttu-id="2319b-109">使用[IMAPIFormMgr:: OpenFormContainer](imapiformmgr-openformcontainer.md)或[IMAPIFormMgr:: SelectFormContainer](imapiformmgr-selectformcontainer.md)方法可选择和打开表单的目标容器。</span><span class="sxs-lookup"><span data-stu-id="2319b-109">Use [IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md) or [IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md) method to select and open the target container for the form.</span></span> 
    
3. <span data-ttu-id="2319b-110">使用[IMAPIFormContainer:: InstallForm](imapiformcontainer-installform.md)函数安装表单。</span><span class="sxs-lookup"><span data-stu-id="2319b-110">Use the [IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md) function to install the form.</span></span> 
    
    <span data-ttu-id="2319b-111">步骤4至6用于安装到本地表单库:</span><span class="sxs-lookup"><span data-stu-id="2319b-111">Steps 4 through 6 are for installation into a local form library:</span></span>
    
4. <span data-ttu-id="2319b-112">将所有文件复制到本地磁盘上的适当位置 (如果安装指向用户工作站上的本地表单库)。</span><span class="sxs-lookup"><span data-stu-id="2319b-112">Copy all files to the appropriate place on the local disk, if installation is to the local form library on the user's workstation.</span></span> <span data-ttu-id="2319b-113">如有必要, 请修改表单配置文件以反映组件的当前路径。</span><span class="sxs-lookup"><span data-stu-id="2319b-113">If necessary, modify the form configuration file to reflect current paths of components.</span></span> <span data-ttu-id="2319b-114">表单配置文件可以包含相对路径, 在这种情况下, 此步骤可能不是必需的。</span><span class="sxs-lookup"><span data-stu-id="2319b-114">The form configuration file can contain relative paths, in which case this step may not be necessary.</span></span>
    
5. <span data-ttu-id="2319b-115">完成相应的 OLE 注册步骤, 将邮件类型与要安装的窗体服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="2319b-115">Complete the appropriate OLE registration steps to associate the message type with the form server being installed.</span></span>
    
6. <span data-ttu-id="2319b-116">如果表单已安装到本地表单库中, 则将表单的图标 (.ico) 和配置 (cfg) 文件复制到%WINDOWS%\FORMS\CONFIGS 目录中, 以便在表单库损坏或删除时可以自动还原表单。</span><span class="sxs-lookup"><span data-stu-id="2319b-116">If the form was installed into the local form library, copy the form's icon (.ico) and configuration (.cfg) files into the %WINDOWS%\FORMS\CONFIGS directory so the form can be automatically restored in case the form library is corrupted or deleted.</span></span> <span data-ttu-id="2319b-117">建议使用此步骤, 但不是强制性步骤。</span><span class="sxs-lookup"><span data-stu-id="2319b-117">This step is recommended but not mandatory.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2319b-118">您可以通过将步骤1和2替换为对[MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md)函数的调用来简化到本地表单库的安装。</span><span class="sxs-lookup"><span data-stu-id="2319b-118">You can simplify installation to a local form library by replacing steps 1 and 2 with a call to the [MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2319b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2319b-119">See also</span></span>



[<span data-ttu-id="2319b-120">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="2319b-120">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

