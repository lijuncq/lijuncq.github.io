---
layout: works
---

<details>
    <summary>PDMS/E3D 二次开发</summary>
    <br>
    <div class="image"><img src="/media/pdms-jtools.png" alt=""></div>
    <h4>1. Engineering design review (pml pmlnet c#)</h4>
    <a>This addin use both pml and pml.net. The form was written in pml and the colorful gridview was written in c#.</a>
    <div class="image"><img src="/media/pdms-design_review.png" alt=""></div>
    <h4>2. Powerlist (pml)</h4>
    <a>A powerful tool to replace the system list tool, You can use this tool to search, add colmuns, subtotal and export.</a>
    <div class="image"><img src="/media/pdms-powerlist.png" alt=""></div>
    <h4>3. Support check (pml)</h4>
    <a>Show support displacement and other info according to stress calculation.</a>
    <div class="image"><img src="/media/pdms-supportcheck.png" alt=""></div>
    <h4>4. Support mto export (pml)</h4>
    <a>Export support mto.</a>
    <div class="image"><img src="/media/pdms-support_mto.png" alt=""></div>
    <h4>5. Other addins</h4>
    <div class="image"><img src="/media/pdms-isodraft.png" alt=""></div>
    <div class="image"><img src="/media/pdms-isorevision.png" alt=""></div>
    <div class="image"><img src="/media/pdms-history.png" alt=""></div>
    <div class="image"><img src="/media/pdms-quicksection.png" alt=""></div>
    <h4>6. Other macros</h4>
    <div class="image"><img src="/media/pdms-macros.png" alt=""></div>
</details>

<details>
    <summary>Navisworks 二次开发</summary>
    <div class="image"><img src="/media/navis-jtools.png" alt=""></div>
    <pre>
        <code>
        public static string Folder2Nwd(string folder, string extensions)
        {
            string reusltNwd = folder + ".nwd";
            List<string> subFolders = new List<string>();

            subFolders = JunCommon.GetAllSubFolders(folder);
            subFolders.Add(folder);
            subFolders.Sort();

            List<List<string>> packages = new List<List<string>>();
            int mainDepth = JunCommon.FolderDepth(folder);
            for(int i=0; i< mainDepth; i++)
            {
                packages.Add(new List<string>());
            }

            foreach(string subFolder in subFolders)
            {
                int depth = JunCommon.FolderDepth(subFolder);
                if(packages.Count < depth)
                {
                    for(int j=packages.Count; j<depth; j++)
                    {
                        packages.Add(new List<string>());
                    }
                }
                packages[depth - 1].Add(subFolder );
            }

            for(int i=packages.Count; i>=mainDepth; i--)
            {
                foreach(string folderPath in packages[i - 1])
                {
                    string listFile = CreateNwdFileList(folderPath, extensions.ToLower());
                    List2Nwd(listFile, listFile.Replace(".lis",".nwd"), NavisApi.DocumentFileVersion.Navisworks2015, NavisApi.Application.MainDocument);
                }
            }

            if (File.Exists(reusltNwd))
                return reusltNwd;
            return "";
        }
        </code>
    </pre>
</details>

<details>
    <summary>Tekla 二次开发</summary>
    <div class="image"><img src="/media/pdms-isorevision.png" alt=""></div>
</details>

<details>
    <summary>AutoCAD 二次开发</summary>
    <div class="image"><img src="/media/pdms-isorevision.png" alt=""></div>
</details>

<details>
    <summary>Django 框架网站</summary>
    <div class="image"><img src="/media/pdms-isorevision.png" alt=""></div>
</details>
