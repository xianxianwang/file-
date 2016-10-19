# file-
文本查询程序
void runquries(ifstream& file)
{
	vector<string>vs;
	map<string,set<int>>ms;
string line;
int i=0;
while(getline(file,line))
{
string word;
istringstream stream(line);
vs.push_back(line);
while(stream>>word)
{
	ms[word].insert(i);
}
i++;
}
cout<<"enter word to look for, or q to quit:";
string s;
if(!(cin>>s)||s=="q")
	cout<<"word is not here"<<endl;
else
{
    cout<<s<<"occurs "<<ms[s].size()<<" times \n";
	for(auto it=ms[s].begin();it!=ms[s].end();it++ )
	{
		cout<<"( line "<<*it<<" ) "<<vs[*it]<<endl;
	}
}
}
int main()
{
 ifstream file("even.txt");
 runquries(file);
 system("pause");
}
