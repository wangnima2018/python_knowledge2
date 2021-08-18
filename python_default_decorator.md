```
@property:
https://www.programiz.com/python-programming/property

It can be act as getters:

    @property
    def statistics_config(self):
        return {
            'suite_stat_level': self['SuiteStatLevel'],
            'tag_stat_include': self['TagStatInclude'],
            'tag_stat_exclude': self['TagStatExclude'],
            'tag_stat_combine': self['TagStatCombine'],
            'tag_stat_link': self['TagStatLink'],
            'tag_doc': self['TagDoc'],
        }
    
    @property
    def result(self):
        if self._result is None:
            include_keywords = bool(self._settings.log or self._settings.output)
            flattened = self._settings.flatten_keywords
            self._result = ExecutionResult(include_keywords=include_keywords,
                                           flattened_keywords=flattened,
                                           merge=self._settings.merge,
                                           rpa=self._settings.rpa,
                                           *self._sources)
            if self._settings.rpa is None:
                self._settings.rpa = self._result.rpa
            modifier = ModelModifier(self._settings.pre_rebot_modifiers,
                                     self._settings.process_empty_suite,
                                     LOGGER)
            self._result.suite.visit(modifier)
            self._result.configure(self._settings.status_rc,
                                   self._settings.suite_config,
                                   self._settings.statistics_config)
            self.return_code = self._result.return_code
        return self._result
        
 why use python property:
 https://www.liaoxuefeng.com/wiki/897692888725344/923030547069856
 https://zhuanlan.zhihu.com/p/64487092
```
