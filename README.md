# My name
Anton
# My contacts
Discord: Anton (@Foreytor)
# About me
I work in a large telecom company, I like to learn new things and improve myself.
# Skills
Python, SAS, Greenplum, ETL
# Example of my code
```python
@method_decorator(csrf_exempt, name='dispatch')
class ConfigToJSON(View):
    http_method_names = ['post']

    def post(self, request):

        if request.FILES:
            try:
                filecfg = request.FILES['filecfg']
                path = 'Kcalibrator.cfg'
                mem_fs = MemoryFS()
                with mem_fs.open(path, "wb", encoding="utf-8") as out:
                    out.writelines(filecfg)
                f_ram = mem_fs.open(path, "r", encoding="utf-8")
                configRequest = SettingClass()
                configRequest.read_config(f_ram)
                mem_fs.close()
                configRequestDict = configRequest.getDict()
                configRequestDict['firmware'] = Firmwares.objects.get(
                    firmware=configRequestDict['firmware']).pk
                configRequestDict['kinematics'] = Kinematics.objects.get(
                    kinimatika=configRequestDict['kinematics']).pk
                configRequestDict['ABL_type'] = AutolevelingType.objects.get(
                    ABL_type=configRequestDict['ABL_type']).pk
                return JsonResponse(configRequestDict, status=200)
            except:
                return HttpResponseBadRequest("Error files")

        else:
            return HttpResponseBadRequest("Error, not files")
```
This code creates a virtual cfg file and converts it to Json which is returned as a response to the client.

# Experience
I support the performance of a large ETL system.
# Education
Bachelor in IT
# Another skills
## Languages:
..* English - A1