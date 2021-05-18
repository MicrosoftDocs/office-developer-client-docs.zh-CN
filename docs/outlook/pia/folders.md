---
title: 文件夹
TOCTitle: Folders
ms:assetid: b72b5705-d77a-4cad-873d-457b9fb6553e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184634(v=office.15)
ms:contentKeyID: 55119856
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ecf342c54d1aa2020fbfad4175a220b2aefecbe3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327180"
---
# <a name="folders"></a><span data-ttu-id="9ba5f-102">文件夹</span><span class="sxs-lookup"><span data-stu-id="9ba5f-102">Folders</span></span>

<span data-ttu-id="9ba5f-p101">本节提供涉及文件夹的示例任务。[Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象表示存储 Microsoft Outlook 项目的文件夹层次结构。文件夹的示例包括"日历"、"邮件"和"已删除邮件"文件夹。在 Outlook 主互操作程序集 (PIA) 中， **Folder** 对象的成员作为 [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) 对象的成员公开。</span><span class="sxs-lookup"><span data-stu-id="9ba5f-p101">This section provides sample tasks that involve folders. [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) objects represent the folder hierarchy where Microsoft Outlook items are stored. Examples of folders include the Calendar, Mail, and Deleted Items folders. In the Outlook Primary Interop Assembly (PIA), members of the **Folder** object are exposed as members of the [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) object.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9ba5f-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="9ba5f-107">In this section</span></span>

|<span data-ttu-id="9ba5f-108">主题</span><span class="sxs-lookup"><span data-stu-id="9ba5f-108">Topic</span></span>|<span data-ttu-id="9ba5f-109">说明</span><span class="sxs-lookup"><span data-stu-id="9ba5f-109">Description</span></span>|
|:----|:----------|
|[<span data-ttu-id="9ba5f-110">将文件夹添加到文件夹列表</span><span class="sxs-lookup"><span data-stu-id="9ba5f-110">Add a folder to the folder list</span></span>](how-to-add-a-folder-to-the-folder-list.md) |<span data-ttu-id="9ba5f-111">介绍了如何使用 [Add(String, Object)](https://msdn.microsoft.com/library/bb645065\(v=office.15\)) 方法将文件夹添加到 Outlook 文件夹列表。</span><span class="sxs-lookup"><span data-stu-id="9ba5f-111">Uses the [Add(String, Object)](https://msdn.microsoft.com/library/bb645065\(v=office.15\)) method to add a folder to the Outlook folder list.</span></span>|
|[<span data-ttu-id="9ba5f-112">枚举文件夹</span><span class="sxs-lookup"><span data-stu-id="9ba5f-112">Enumerate folders</span></span>](how-to-enumerate-folders.md)  |<span data-ttu-id="9ba5f-113">介绍了如何通过循环访问文件夹集合来枚举文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ba5f-113">Enumerates folders by iterating through a collection of folders.</span></span>|
|[<span data-ttu-id="9ba5f-114">获取默认文件夹并枚举它的子文件夹</span><span class="sxs-lookup"><span data-stu-id="9ba5f-114">Get a default folder and enumerate its subfolders</span></span>](how-to-get-a-default-folder-and-enumerate-its-subfolders.md) |<span data-ttu-id="9ba5f-115">介绍了如何获取用户默认存储中的默认文件夹，并枚举它的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ba5f-115">Obtains a default folder in the user’s default store and enumerates its subfolders.</span></span>|
|[<span data-ttu-id="9ba5f-116">根据文件夹路径获取文件夹</span><span class="sxs-lookup"><span data-stu-id="9ba5f-116">Get a folder based on its folder path</span></span>](how-to-get-a-folder-based-on-its-folder-path.md)  |<span data-ttu-id="9ba5f-117">介绍了如何先获取文件夹路径，再获取关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ba5f-117">Takes a folder path and obtains the associated folder.</span></span>|
|[<span data-ttu-id="9ba5f-118">选择文件夹并显示文件夹信息</span><span class="sxs-lookup"><span data-stu-id="9ba5f-118">Select a folder and display folder information</span></span>](how-to-select-a-folder-and-display-folder-information.md)  |<span data-ttu-id="9ba5f-119">介绍了如何以编程方式显示用户从指定文件夹列表中选择的文件夹的相关信息。</span><span class="sxs-lookup"><span data-stu-id="9ba5f-119">Programmatically displays information about a folder that a user selects from a specified folder list.</span></span>|
|[<span data-ttu-id="9ba5f-120">获取文件夹的默认邮件类别</span><span class="sxs-lookup"><span data-stu-id="9ba5f-120">Get the default message class of a folder</span></span>](how-to-get-the-default-message-class-of-a-folder.md)  |<span data-ttu-id="9ba5f-121">介绍了如何使用 [DefaultMessageClass](https://msdn.microsoft.com/library/bb646541\(v=office.15\)) 属性获取文件夹的默认邮件类别。</span><span class="sxs-lookup"><span data-stu-id="9ba5f-121">Uses the [DefaultMessageClass](https://msdn.microsoft.com/library/bb646541\(v=office.15\)) property to obtain the default message class of a folder.</span></span>|
|[<span data-ttu-id="9ba5f-122">访问在文件夹中存储为隐藏邮件的解决方案专用数据</span><span class="sxs-lookup"><span data-stu-id="9ba5f-122">Access solution-specific data stored as a hidden message in a folder</span></span>](how-to-access-solution-specific-data-stored-as-a-hidden-message-in-a-folder.md)  |<span data-ttu-id="9ba5f-123">介绍了如何使用 [StorageItem](https://msdn.microsoft.com/library/bb623436\(v=office.15\)) 对象来检索在文件夹中存储为特定邮件类别隐藏邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="9ba5f-123">Uses the [StorageItem](https://msdn.microsoft.com/library/bb623436\(v=office.15\)) object to retrieve data that is stored as a hidden message of a specific message class in a folder.</span></span>|
|[<span data-ttu-id="9ba5f-124">确保文件夹级查询支持自定义项属性</span><span class="sxs-lookup"><span data-stu-id="9ba5f-124">Ensure that custom item properties are supported in folder-level queries</span></span>](how-to-ensure-that-custom-item-properties-are-supported-in-folder-level-queries.md) |<span data-ttu-id="9ba5f-125">演示如何确保在向项目类型中添加自定义属性时，也会将该属性添加到文件夹中，以便在文件夹级别查询该自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9ba5f-125">Shows how to ensure that when you add a custom property to an item type, you also add the property to the folder so that you can query on that custom property at the folder level.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9ba5f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ba5f-126">See also</span></span>

- [<span data-ttu-id="9ba5f-127">日历</span><span class="sxs-lookup"><span data-stu-id="9ba5f-127">Calendar</span></span>](calendar.md)
- [<span data-ttu-id="9ba5f-128">联系人</span><span class="sxs-lookup"><span data-stu-id="9ba5f-128">Contacts</span></span>](contacts.md)
- [<span data-ttu-id="9ba5f-129">邮件</span><span class="sxs-lookup"><span data-stu-id="9ba5f-129">Mail</span></span>](mail.md)
- [<span data-ttu-id="9ba5f-130">我如何...（Outlook 2013 PIA 参考）</span><span class="sxs-lookup"><span data-stu-id="9ba5f-130">How do I... (Outlook 2013 PIA reference)</span></span>](how-do-i-outlook-2013-pia-reference.md)

