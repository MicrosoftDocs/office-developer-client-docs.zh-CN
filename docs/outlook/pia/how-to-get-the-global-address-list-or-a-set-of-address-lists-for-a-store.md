---
title: 获取存储的全局地址列表或一组地址列表
TOCTitle: Get the Global Address List or a set of address lists for a store
ms:assetid: a361ac58-25c6-4ce1-97b0-403ad67ee7a4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184631(v=office.15)
ms:contentKeyID: 55119800
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 582b0e836edc361d1d8717f94a5d7490c57cd530
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320116"
---
# <a name="get-the-global-address-list-or-a-set-of-address-lists-for-a-store"></a><span data-ttu-id="87e99-102">获取存储的全局地址列表或一组地址列表</span><span class="sxs-lookup"><span data-stu-id="87e99-102">Get the Global Address List or a set of address lists for a store</span></span>

<span data-ttu-id="87e99-103">本主题包含两个代码示例，它们演示如何获取与存储相关的全局地址列表 (GAL)，以及如何获取与存储相关的所有地址列表。</span><span class="sxs-lookup"><span data-stu-id="87e99-103">This topic contains two code examples that show how to get the Global Address List (GAL) that is associated with a store, and how to get all of the address lists that are associated with a store.</span></span>

## <a name="example"></a><span data-ttu-id="87e99-104">示例</span><span class="sxs-lookup"><span data-stu-id="87e99-104">Example</span></span>

<span data-ttu-id="87e99-105">在配置文件中定义了多个 Exchange 帐户的 Outlook 会话中，可以有多个与存储关联的地址列表。</span><span class="sxs-lookup"><span data-stu-id="87e99-105">In an Outlook session where multiple Exchange accounts are defined in the profile, there can be multiple address lists associated with a store.</span></span> <span data-ttu-id="87e99-106">在下面的各个代码示例中，受关注的特定存储是活动的资源管理器中显示的当前文件夹的存储，但用于获取全局地址列表或存储的一组 [AddressList](https://msdn.microsoft.com/library/bb623538\(v=office.15\)) 对象的算法适用于任何 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="87e99-106">In each of the following code examples, the specific store of interest is the store for the current folder displayed in the active explorer, but the algorithm to get a Global Address List or a set of [AddressList](https://msdn.microsoft.com/library/bb623538\(v=office.15\)) objects for a store applies to any Exchange store.</span></span>

<span data-ttu-id="87e99-107">第一个代码示例包含 DisplayGlobalAddressListForStore 方法和 GetGlobalAddressList 函数。</span><span class="sxs-lookup"><span data-stu-id="87e99-107">The first code example contains the DisplayGlobalAddressListForStore method and the GetGlobalAddressList function.</span></span> <span data-ttu-id="87e99-108">DisplayGlobalAddressListForStore 方法会在“**选择姓名**”对话框中显示与当前存储相关联的全局地址列表。</span><span class="sxs-lookup"><span data-stu-id="87e99-108">The DisplayGlobalAddressListForStore method displays, in the **Select Names** dialog box, the Global Address List that is associated with the current store.</span></span> <span data-ttu-id="87e99-109">DisplayGlobalAddressListForStore 会首先获取当前存储。</span><span class="sxs-lookup"><span data-stu-id="87e99-109">DisplayGlobalAddressListForStore first obtains the current store.</span></span> <span data-ttu-id="87e99-110">如果当前存储是 Exchange 存储，系统会调用 GetGlobalAddressList 以获得与当前存储关联的全局地址列表。</span><span class="sxs-lookup"><span data-stu-id="87e99-110">If the current store is an Exchange store, GetGlobalAddressList is called to obtain the Global Address List associated with the current store.</span></span> 

<span data-ttu-id="87e99-111">GetGlobalAddressList 会使用 [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象和 MAPI 属性 https://schemas.microsoft.com/mapi/proptag/0x3D150102 来获取地址列表和当前存储的 PR\_EMSMDB\_SECTION\_UID 属性。</span><span class="sxs-lookup"><span data-stu-id="87e99-111">GetGlobalAddressList uses the [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) object and the MAPI property https://schemas.microsoft.com/mapi/proptag/0x3D150102 to obtain the PR\_EMSMDB\_SECTION\_UID property of an address list and the current store.</span></span> <span data-ttu-id="87e99-112">如果它们的 PR\_EMSMDB\_SECTION\_UID 属性匹配，那么 GetGlobalAddressList 会将地址列表识别为与存储关联，而且如果地址列表的 [AddressListType](https://msdn.microsoft.com/library/bb610942\(v=office.15\)) 属性是 [olExchangeGlobalAddressList](https://msdn.microsoft.com/library/bb644009\(v=office.15\))，那么地址列表便是全局地址列表。</span><span class="sxs-lookup"><span data-stu-id="87e99-112">GetGlobalAddressList identifies an address list as associated with a store if their PR\_EMSMDB\_SECTION\_UID properties match, and the address list is the Global Address List if its [AddressListType](https://msdn.microsoft.com/library/bb610942\(v=office.15\)) property is [olExchangeGlobalAddressList](https://msdn.microsoft.com/library/bb644009\(v=office.15\)).</span></span> <span data-ttu-id="87e99-113">如果对 GetGlobalAddressList 的调用成功，DisplayGlobalAddressListForStore 会使用 [SelectNamesDialog](https://msdn.microsoft.com/library/bb609866\(v=office.15\)) 对象来在“**选择姓名**”对话框中显示返回的全局地址列表。</span><span class="sxs-lookup"><span data-stu-id="87e99-113">If the call to GetGlobalAddressList succeeds, DisplayGlobalAddressListForStore uses the [SelectNamesDialog](https://msdn.microsoft.com/library/bb609866\(v=office.15\)) object to display the returned Global Address List in the **Select Names** dialog box.</span></span>

<span data-ttu-id="87e99-114">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="87e99-114">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="87e99-115">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="87e99-115">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="87e99-116">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="87e99-116">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
void DisplayGlobalAddressListForStore()
{
    Outlook.Folder currentFolder =
        Application.ActiveExplorer().CurrentFolder
        as Outlook.Folder;
    Outlook.Store currentStore = currentFolder.Store;
    if (currentStore.ExchangeStoreType !=
        Outlook.OlExchangeStoreType.olNotExchange)
    {
        Outlook.SelectNamesDialog snd = 
            Application.Session.GetSelectNamesDialog();
        Outlook.AddressList addrList = 
            GetGlobalAddressList(currentStore);
        if (addrList != null)
        {
            snd.InitialAddressList = addrList;
            snd.Display();
        }
    }
}

public Outlook.AddressList GetGlobalAddressList(Outlook.Store store)
{
    string  PR_EMSMDB_SECTION_UID = 
        @"https://schemas.microsoft.com/mapi/proptag/0x3D150102";
    if (store == null)
    {
        throw new ArgumentNullException();
    }
    Outlook.PropertyAccessor oPAStore = store.PropertyAccessor;
    string storeUID = oPAStore.BinaryToString(
        oPAStore.GetProperty(PR_EMSMDB_SECTION_UID));
    foreach (Outlook.AddressList addrList 
        in Application.Session.AddressLists)
    {
        Outlook.PropertyAccessor oPAAddrList = 
            addrList.PropertyAccessor;
        string addrListUID = oPAAddrList.BinaryToString(
            oPAAddrList.GetProperty(PR_EMSMDB_SECTION_UID));
        // Return addrList if match on storeUID
        // and type is olExchangeGlobalAddressList.
        if (addrListUID == storeUID && addrList.AddressListType ==
            Outlook.OlAddressListType.olExchangeGlobalAddressList)
        {
            return addrList;
        }
    }
    return null;
}
```

<span data-ttu-id="87e99-117">第二个代码示例包含 EnumerateAddressListsForStore 方法和 GetAddressLists 函数。</span><span class="sxs-lookup"><span data-stu-id="87e99-117">The second code example contains the EnumerateAddressListsForStore method and GetAddressLists function.</span></span> <span data-ttu-id="87e99-118">EnumerateAddressListsForStore 方法会显示为当前存储定义的每个地址列表的类型和解析顺序。</span><span class="sxs-lookup"><span data-stu-id="87e99-118">The EnumerateAddressListsForStore method displays the type and resolution order of each address list defined for the current store.</span></span> <span data-ttu-id="87e99-119">EnumerateAddressListsForStore 会首先获取当前存储，然后调用 GetAddressLists 来获取包含当前存储的 AddressList 对象的 .NET Framework 泛型 [List\<T\>](https://msdn.microsoft.com/en-us/library/6sh2ey19) 对象。</span><span class="sxs-lookup"><span data-stu-id="87e99-119">EnumerateAddressListsForStore first obtains the current store, and then calls GetAddressLists to obtain a .NET Framework generic [List\<T\>](https://msdn.microsoft.com/en-us/library/6sh2ey19) object that contains AddressList objects for the current store.</span></span> 

<span data-ttu-id="87e99-120">GetAddressLists 会枚举为会话定义的各地址列表，使用 PropertyAccessor 对象和 MAPI 命名属性 https://schemas.microsoft.com/mapi/proptag/0x3D150102 来获取地址列表的 PR\_EMSMDB\_SECTION\_UID 属性和当前存储的 PR\_EMSMDB\_SECTION\_UID 属性。</span><span class="sxs-lookup"><span data-stu-id="87e99-120">GetAddressLists enumerates each address list defined for the session, uses the PropertyAccessor object and the MAPI named property https://schemas.microsoft.com/mapi/proptag/0x3D150102 to obtain the PR\_EMSMDB\_SECTION\_UID property of an address list, and the PR\_EMSMDB\_SECTION\_UID property of a current store.</span></span> <span data-ttu-id="87e99-121">如果它们的 PR\_EMSMDB\_SECTION\_UID 属性互相匹配，则 GetGlobalAddressList 会将地址列表识别为与存储关联，并返回当前存储的一组地址列表。</span><span class="sxs-lookup"><span data-stu-id="87e99-121">GetGlobalAddressList identifies an address list as associated with a store if their PR\_EMSMDB\_SECTION\_UID properties match, and returns a set of address lists for the current store.</span></span> <span data-ttu-id="87e99-122">然后， EnumerateAddressListsForStore 会使用 **AddressList** 对象的 [AddressListType](https://msdn.microsoft.com/library/bb610942\(v=office.15\)) 和 [ResolutionOrder](https://msdn.microsoft.com/library/bb646853\(v=office.15\)) 属性来显示返回的每个地址列表的类型和解析顺序。</span><span class="sxs-lookup"><span data-stu-id="87e99-122">EnumerateAddressListsForStore then uses the [AddressListType](https://msdn.microsoft.com/library/bb610942\(v=office.15\)) and [ResolutionOrder](https://msdn.microsoft.com/library/bb646853\(v=office.15\)) properties of the **AddressList** object to display the type and resolution order for each returned address list.</span></span>

```csharp
private void EnumerateAddressListsForStore()
{
    Outlook.Folder currentFolder =
        Application.ActiveExplorer().CurrentFolder
        as Outlook.Folder;
    Outlook.Store currentStore = currentFolder.Store;
    List<Outlook.AddressList> addrListsForStore = 
        GetAddressLists(currentStore);
    foreach (Outlook.AddressList addrList in addrListsForStore)
    {
        Debug.WriteLine(addrList.Name 
            + " " + addrList.AddressListType.ToString()
            + " Resolution Order: " +
            addrList.ResolutionOrder);
    }
}
public List<Outlook.AddressList> GetAddressLists(Outlook.Store store)
{
    List<Outlook.AddressList> addrLists = 
        new List<Microsoft.Office.Interop.Outlook.AddressList>();
    string PR_EMSMDB_SECTION_UID =
        @"https://schemas.microsoft.com/mapi/proptag/0x3D150102";
    if (store == null)
    {
        throw new ArgumentNullException();
    }
    Outlook.PropertyAccessor oPAStore = store.PropertyAccessor;
    string storeUID = oPAStore.BinaryToString(
        oPAStore.GetProperty(PR_EMSMDB_SECTION_UID));
    foreach (Outlook.AddressList addrList
        in Application.Session.AddressLists)
    {
        Outlook.PropertyAccessor oPAAddrList =
            addrList.PropertyAccessor;
        string addrListUID = oPAAddrList.BinaryToString(
            oPAAddrList.GetProperty(PR_EMSMDB_SECTION_UID));
        // Return addrList if match on storeUID
        // and type is olExchangeGlobalAddressList.
        if (addrListUID == storeUID)
        {
            addrLists.Add(addrList);
        }
    }
    return addrLists;
}
```

## <a name="see-also"></a><span data-ttu-id="87e99-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87e99-123">See also</span></span>

- [<span data-ttu-id="87e99-124">通讯簿</span><span class="sxs-lookup"><span data-stu-id="87e99-124">Address book</span></span>](address-book.md)

