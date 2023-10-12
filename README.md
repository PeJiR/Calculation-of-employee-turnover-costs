#  Calculation of employee turnover costs
<a href="https://github.com/PeJiR/Calculation-of-employee-turnover-costs.git" target="_blank"> <img border=0 src="https://img.shields.io/badge/python-2.7,%203.6+-blue.svg?style=flat" alt="Python version"></a>
<a href="https://github.com/PeJiR/Calculation-of-employee-turnover-costs.git" target="_blank"><img src="https://img.shields.io/pypi/status/ezibpy.svg?maxAge=60" alt="status"/></a>
<a target="new" href="https://github.com/PeJiR/Calculation-of-employee-turnover-costs.git"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FPeJiR%2FCalculation-of-employee-turnover-costs.git&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=Views&edge_flat=false"/></a>
<a target="new" href="https://github.com/PeJiR/Calculation-of-employee-turnover-costs "><img border=0 src="https://img.shields.io/github/stars/Pejir/Calculation-of-employee-turnover-costs .svg?style=social&label=Star&maxAge=60" alt="Star this repo"></a>
<a href="https://www.linkedin.com/in/pejir/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin&labelColor=blue" alt="LinkedIn" /></a>

---

Employee turnover costs calculation is the process of determining the financial impact of employee turnover on a business. It includes both direct and indirect costs, such as:

- **Direct costs**:
  - Recruiting and hiring costs (e.g., advertising, job boards, recruiter fees)
  - Onboarding and training costs
  - Severance pay and unused vacation time
- **Indirect costs:**
  - Lost productivity
  - Decreased morale
  - Disruption to workflow
  - Customer dissatisfaction

The cost of employee turnover can vary widely depending on the industry, the employee's role, and the reason for leaving. However, it is generally estimated to cost between 50% and 200% of the employee's annual salary to replace them.

To calculate the cost of employee turnover, businesses can use the following formula:

Cost of employee turnover = (Number of employees who left / Total number of employees) * Average cost per employee turnover

The average cost per employee turnover can be calculated by adding up the direct and indirect costs associated with employee turnover and dividing by the number of employees who left.

Once businesses have calculated the cost of employee turnover, they can use this information to develop strategies to reduce turnover and improve employee retention.

By reducing employee turnover, businesses can save money and improve their bottom line.
### Project Steps
[<img src = "project.png">](TPS_Dia_1_Configuracion.ipynb)

### [Project Notebook](https://github.com/PeJiR/Calculation-of-employee-turnover-costs/blob/main/Employee%20turnover%20costs%20calculation.ipynb)

### [Dashboard in Tableau](https://public.tableau.com/shared/P6PGN3KPC?:display_count=n&:origin=viz_share_link )

 [<img src = "Tableau.png">](https://public.tableau.com/shared/P6PGN3KPC?:display_count=n&:origin=viz_share_link)

```python
{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "3ac32b91",
   "metadata": {
    "papermill": {
     "duration": 0.013021,
     "end_time": "2023-10-05T21:57:09.004411",
     "exception": false,
     "start_time": "2023-10-05T21:57:08.991390",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "# Calculation-of-employee-turnover-costs\n",
    " "
   ]
  },
  {
   "cell_type": "markdown",
   "id": "81a2a926",
   "metadata": {
    "id": "bOpscQ6drkRi",
    "papermill": {
     "duration": 0.012183,
     "end_time": "2023-10-05T21:57:09.029202",
     "exception": false,
     "start_time": "2023-10-05T21:57:09.017019",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "## Project kickoff"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "4b1d63d7",
   "metadata": {
    "id": "MKUOBPsiKK1w",
    "papermill": {
     "duration": 0.012784,
     "end_time": "2023-10-05T21:57:09.054531",
     "exception": false,
     "start_time": "2023-10-05T21:57:09.041747",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "### Importing libraries"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "d953ecaa",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2023-10-05T21:57:09.082562Z",
     "iopub.status.busy": "2023-10-05T21:57:09.082004Z",
     "iopub.status.idle": "2023-10-05T21:57:11.199440Z",
     "shell.execute_reply": "2023-10-05T21:57:11.198352Z"
    },
    "id": "mU92c65BKN-D",
    "papermill": {
     "duration": 2.134517,
     "end_time": "2023-10-05T21:57:11.201842",
     "exception": false,
     "start_time": "2023-10-05T21:57:09.067325",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "import numpy as np\n",
    "import pandas as pd\n",
    "import matplotlib.pyplot as plt\n",
    "import sklearn as skl\n",
    "%matplotlib inline"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "b8c2ef39",
   "metadata": {
    "id": "ANoZnP39rr1r",
    "papermill": {
     "duration": 0.012396,
     "end_time": "2023-10-05T21:57:11.227849",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.215453",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "### DATA UPLOAD"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "00ff1e89",
   "metadata": {
    "id": "ejI_fsyyr_Nb",
    "papermill": {
     "duration": 0.012162,
     "end_time": "2023-10-05T21:57:11.252549",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.240387",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "Before continuing you must:\n",
    "\n",
    "* Have downloaded the data from the platform\n",
    "\n",
    "* Have unzipped them in a folder on your hard drive\n",
    "\n",
    "* Have uploaded them to Colab using the file explorer (folder icon - upload file icon)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "id": "f45e3d71",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2023-10-05T21:57:11.280649Z",
     "iopub.status.busy": "2023-10-05T21:57:11.279304Z",
     "iopub.status.idle": "2023-10-05T21:57:11.385824Z",
     "shell.execute_reply": "2023-10-05T21:57:11.385058Z"
    },
    "papermill": {
     "duration": 0.122201,
     "end_time": "2023-10-05T21:57:11.387630",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.265429",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>age</th>\n",
       "      <th>turnover</th>\n",
       "      <th>travel</th>\n",
       "      <th>department</th>\n",
       "      <th>distance</th>\n",
       "      <th>education</th>\n",
       "      <th>career</th>\n",
       "      <th>employee</th>\n",
       "      <th>satisfaction_environment</th>\n",
       "      <th>sex</th>\n",
       "      <th>...</th>\n",
       "      <th>satisfaction_colleagues</th>\n",
       "      <th>fortnight_hours</th>\n",
       "      <th>action_level</th>\n",
       "      <th>years_experience</th>\n",
       "      <th>num_formations_last_year</th>\n",
       "      <th>conciliation</th>\n",
       "      <th>years_company</th>\n",
       "      <th>years_in_position</th>\n",
       "      <th>years_since_last_promotion</th>\n",
       "      <th>years_with_current_manager</th>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>id</th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>1.0</th>\n",
       "      <td>41.0</td>\n",
       "      <td>Yes</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Sales</td>\n",
       "      <td>1.0</td>\n",
       "      <td>University</td>\n",
       "      <td>Life Sciences</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Medium</td>\n",
       "      <td>3.0</td>\n",
       "      <td>...</td>\n",
       "      <td>Low</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>8.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>6.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>0.0</td>\n",
       "      <td>5.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2.0</th>\n",
       "      <td>49.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Frequently</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>8.0</td>\n",
       "      <td>Secondary</td>\n",
       "      <td>Life Sciences</td>\n",
       "      <td>1.0</td>\n",
       "      <td>High</td>\n",
       "      <td>2.0</td>\n",
       "      <td>...</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>80.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>10.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>10.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>1.0</td>\n",
       "      <td>7.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4.0</th>\n",
       "      <td>37.0</td>\n",
       "      <td>Yes</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>2.0</td>\n",
       "      <td>Secondary</td>\n",
       "      <td>Other</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>2.0</td>\n",
       "      <td>...</td>\n",
       "      <td>Medium</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>7.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>0.0</td>\n",
       "      <td>2.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>0.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5.0</th>\n",
       "      <td>33.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Frequently</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>3.0</td>\n",
       "      <td>University</td>\n",
       "      <td>Life Sciences</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>3.0</td>\n",
       "      <td>...</td>\n",
       "      <td>High</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>8.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>8.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>0.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>7.0</th>\n",
       "      <td>27.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>2.0</td>\n",
       "      <td>University</td>\n",
       "      <td>Medical</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Low</td>\n",
       "      <td>3.0</td>\n",
       "      <td>...</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>80.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>6.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2.0</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>...</th>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2062.0</th>\n",
       "      <td>39.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>6.0</td>\n",
       "      <td>Secondary</td>\n",
       "      <td>Medical</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>2.0</td>\n",
       "      <td>...</td>\n",
       "      <td>Low</td>\n",
       "      <td>80.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>9.0</td>\n",
       "      <td>5.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>7.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>1.0</td>\n",
       "      <td>7.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2064.0</th>\n",
       "      <td>27.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>4.0</td>\n",
       "      <td>Master</td>\n",
       "      <td>Life Sciences</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Medium</td>\n",
       "      <td>4.0</td>\n",
       "      <td>...</td>\n",
       "      <td>Medium</td>\n",
       "      <td>80.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>6.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>6.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>0.0</td>\n",
       "      <td>3.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2065.0</th>\n",
       "      <td>49.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Frequently</td>\n",
       "      <td>Sales</td>\n",
       "      <td>2.0</td>\n",
       "      <td>Secondary</td>\n",
       "      <td>Medical</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>NaN</td>\n",
       "      <td>...</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>17.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>9.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>0.0</td>\n",
       "      <td>8.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2068.0</th>\n",
       "      <td>34.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>8.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>Medical</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Medium</td>\n",
       "      <td>4.0</td>\n",
       "      <td>...</td>\n",
       "      <td>Low</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>6.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>4.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>1.0</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>NaN</th>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>...</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>1471 rows × 31 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "         age turnover             travel              department  distance  \\\n",
       "id                                                                           \n",
       "1.0     41.0      Yes      Travel_Rarely                   Sales       1.0   \n",
       "2.0     49.0       No  Travel_Frequently  Research & Development       8.0   \n",
       "4.0     37.0      Yes      Travel_Rarely  Research & Development       2.0   \n",
       "5.0     33.0       No  Travel_Frequently  Research & Development       3.0   \n",
       "7.0     27.0       No      Travel_Rarely  Research & Development       2.0   \n",
       "...      ...      ...                ...                     ...       ...   \n",
       "2062.0  39.0       No      Travel_Rarely  Research & Development       6.0   \n",
       "2064.0  27.0       No      Travel_Rarely  Research & Development       4.0   \n",
       "2065.0  49.0       No  Travel_Frequently                   Sales       2.0   \n",
       "2068.0  34.0       No      Travel_Rarely  Research & Development       8.0   \n",
       "NaN      NaN      NaN                NaN                     NaN       NaN   \n",
       "\n",
       "         education         career  employee satisfaction_environment  sex  \\\n",
       "id                                                                          \n",
       "1.0     University  Life Sciences       1.0                   Medium  3.0   \n",
       "2.0      Secondary  Life Sciences       1.0                     High  2.0   \n",
       "4.0      Secondary          Other       1.0                Very_High  2.0   \n",
       "5.0     University  Life Sciences       1.0                Very_High  3.0   \n",
       "7.0     University        Medical       1.0                      Low  3.0   \n",
       "...            ...            ...       ...                      ...  ...   \n",
       "2062.0   Secondary        Medical       1.0                Very_High  2.0   \n",
       "2064.0      Master  Life Sciences       1.0                   Medium  4.0   \n",
       "2065.0   Secondary        Medical       1.0                Very_High  NaN   \n",
       "2068.0         NaN        Medical       1.0                   Medium  4.0   \n",
       "NaN            NaN            NaN       NaN                      NaN  NaN   \n",
       "\n",
       "        ... satisfaction_colleagues  fortnight_hours action_level  \\\n",
       "id      ...                                                         \n",
       "1.0     ...                     Low             80.0          0.0   \n",
       "2.0     ...               Very_High             80.0          1.0   \n",
       "4.0     ...                  Medium             80.0          0.0   \n",
       "5.0     ...                    High             80.0          0.0   \n",
       "7.0     ...               Very_High             80.0          1.0   \n",
       "...     ...                     ...              ...          ...   \n",
       "2062.0  ...                     Low             80.0          1.0   \n",
       "2064.0  ...                  Medium             80.0          1.0   \n",
       "2065.0  ...               Very_High             80.0          0.0   \n",
       "2068.0  ...                     Low             80.0          0.0   \n",
       "NaN     ...                     NaN              NaN          NaN   \n",
       "\n",
       "       years_experience num_formations_last_year  conciliation  years_company  \\\n",
       "id                                                                              \n",
       "1.0                 8.0                      0.0           NaN            6.0   \n",
       "2.0                10.0                      3.0           NaN           10.0   \n",
       "4.0                 7.0                      3.0           NaN            0.0   \n",
       "5.0                 8.0                      3.0           NaN            8.0   \n",
       "7.0                 6.0                      3.0           NaN            2.0   \n",
       "...                 ...                      ...           ...            ...   \n",
       "2062.0              9.0                      5.0           NaN            7.0   \n",
       "2064.0              6.0                      0.0           NaN            6.0   \n",
       "2065.0             17.0                      3.0           NaN            9.0   \n",
       "2068.0              6.0                      3.0     Very_High            4.0   \n",
       "NaN                 NaN                      NaN           NaN            NaN   \n",
       "\n",
       "       years_in_position years_since_last_promotion  \\\n",
       "id                                                    \n",
       "1.0                  NaN                        0.0   \n",
       "2.0                  NaN                        1.0   \n",
       "4.0                  2.0                        0.0   \n",
       "5.0                  3.0                        3.0   \n",
       "7.0                  NaN                        2.0   \n",
       "...                  ...                        ...   \n",
       "2062.0               NaN                        1.0   \n",
       "2064.0               NaN                        0.0   \n",
       "2065.0               NaN                        0.0   \n",
       "2068.0               NaN                        1.0   \n",
       "NaN                  NaN                        NaN   \n",
       "\n",
       "        years_with_current_manager  \n",
       "id                                  \n",
       "1.0                            5.0  \n",
       "2.0                            7.0  \n",
       "4.0                            0.0  \n",
       "5.0                            0.0  \n",
       "7.0                            2.0  \n",
       "...                            ...  \n",
       "2062.0                         7.0  \n",
       "2064.0                         3.0  \n",
       "2065.0                         8.0  \n",
       "2068.0                         2.0  \n",
       "NaN                            NaN  \n",
       "\n",
       "[1471 rows x 31 columns]"
      ]
     },
     "execution_count": 2,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df = pd.read_csv(\"/kaggle/input/employees-turnover-costs-calculations/Employee turnover costs calculations.csv\", sep=\",\", index_col=\"id\", na_values=\"#N/D\")\n",
    "df"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "8b9b0d57",
   "metadata": {
    "papermill": {
     "duration": 0.013437,
     "end_time": "2023-10-05T21:57:11.414201",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.400764",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "## BUSINESS ANALYTICS"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "id": "6d9ca610",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2023-10-05T21:57:11.503735Z",
     "iopub.status.busy": "2023-10-05T21:57:11.503063Z",
     "iopub.status.idle": "2023-10-05T21:57:11.524616Z",
     "shell.execute_reply": "2023-10-05T21:57:11.523335Z"
    },
    "papermill": {
     "duration": 0.099808,
     "end_time": "2023-10-05T21:57:11.527157",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.427349",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "Index: 1471 entries, 1.0 to nan\n",
      "Data columns (total 31 columns):\n",
      " #   Column                      Non-Null Count  Dtype  \n",
      "---  ------                      --------------  -----  \n",
      " 0   age                         1470 non-null   float64\n",
      " 1   turnover                    1470 non-null   object \n",
      " 2   travel                      1470 non-null   object \n",
      " 3   department                  1470 non-null   object \n",
      " 4   distance                    1470 non-null   float64\n",
      " 5   education                   1369 non-null   object \n",
      " 6   career                      1470 non-null   object \n",
      " 7   employee                    1470 non-null   float64\n",
      " 8   satisfaction_environment    1470 non-null   object \n",
      " 9   sex                         1271 non-null   float64\n",
      " 10  implicatio                  1452 non-null   object \n",
      " 11  job_level                   1470 non-null   float64\n",
      " 12  job                         1470 non-null   object \n",
      " 13  satisfation_job             1394 non-null   object \n",
      " 14  civil_Status                1470 non-null   object \n",
      " 15  monthly_salary              1470 non-null   float64\n",
      " 16  num_previous_companies      1470 non-null   float64\n",
      " 17  Older                       1470 non-null   object \n",
      " 18  Extra hours                 1470 non-null   object \n",
      " 19  salary_increase             1470 non-null   float64\n",
      " 20  assessment                  1470 non-null   object \n",
      " 21  satisfaction_colleagues     1470 non-null   object \n",
      " 22  fortnight_hours             1470 non-null   float64\n",
      " 23  action_level                1470 non-null   float64\n",
      " 24  years_experience            1470 non-null   float64\n",
      " 25  num_formations_last_year    1470 non-null   float64\n",
      " 26  conciliation                459 non-null    object \n",
      " 27  years_company               1470 non-null   float64\n",
      " 28  years_in_position           232 non-null    float64\n",
      " 29  years_since_last_promotion  1470 non-null   float64\n",
      " 30  years_with_current_manager  1470 non-null   float64\n",
      "dtypes: float64(16), object(15)\n",
      "memory usage: 367.8+ KB\n"
     ]
    }
   ],
   "source": [
    "df.info()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "id": "3085421f",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2023-10-05T21:57:11.563505Z",
     "iopub.status.busy": "2023-10-05T21:57:11.562531Z",
     "iopub.status.idle": "2023-10-05T21:57:11.576394Z",
     "shell.execute_reply": "2023-10-05T21:57:11.575413Z"
    },
    "papermill": {
     "duration": 0.034814,
     "end_time": "2023-10-05T21:57:11.578418",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.543604",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "years_in_position             1239\n",
       "conciliation                  1012\n",
       "sex                            200\n",
       "education                      102\n",
       "satisfation_job                 77\n",
       "implicatio                      19\n",
       "age                              1\n",
       "action_level                     1\n",
       "assessment                       1\n",
       "satisfaction_colleagues          1\n",
       "fortnight_hours                  1\n",
       "years_experience                 1\n",
       "Extra hours                      1\n",
       "num_formations_last_year         1\n",
       "years_company                    1\n",
       "years_since_last_promotion       1\n",
       "salary_increase                  1\n",
       "monthly_salary                   1\n",
       "Older                            1\n",
       "num_previous_companies           1\n",
       "turnover                         1\n",
       "civil_Status                     1\n",
       "job                              1\n",
       "job_level                        1\n",
       "satisfaction_environment         1\n",
       "employee                         1\n",
       "career                           1\n",
       "distance                         1\n",
       "department                       1\n",
       "travel                           1\n",
       "years_with_current_manager       1\n",
       "dtype: int64"
      ]
     },
     "execution_count": 4,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.isna().sum().sort_values(ascending = False)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "b29fb9f4",
   "metadata": {
    "papermill": {
     "duration": 0.017893,
     "end_time": "2023-10-05T21:57:11.623006",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.605113",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "### Conclusions\n",
    "* Years in position and reconciliation have too many nulls --> eliminate variables\n",
    "* Sex, education, job_satisfaction and involvement --> impute them after EDA"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "id": "0c6c3dfb",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2023-10-05T21:57:11.673348Z",
     "iopub.status.busy": "2023-10-05T21:57:11.672702Z",
     "iopub.status.idle": "2023-10-05T21:57:11.678624Z",
     "shell.execute_reply": "2023-10-05T21:57:11.677750Z"
    },
    "papermill": {
     "duration": 0.033961,
     "end_time": "2023-10-05T21:57:11.680683",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.646722",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df.drop(columns= ['years_in_position','conciliation'], inplace= True)\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "id": "73b24eae",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2023-10-05T21:57:11.718329Z",
     "iopub.status.busy": "2023-10-05T21:57:11.717938Z",
     "iopub.status.idle": "2023-10-05T21:57:11.752269Z",
     "shell.execute_reply": "2023-10-05T21:57:11.751066Z"
    },
    "papermill": {
     "duration": 0.052811,
     "end_time": "2023-10-05T21:57:11.754500",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.701689",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>age</th>\n",
       "      <th>turnover</th>\n",
       "      <th>travel</th>\n",
       "      <th>department</th>\n",
       "      <th>distance</th>\n",
       "      <th>education</th>\n",
       "      <th>career</th>\n",
       "      <th>employee</th>\n",
       "      <th>satisfaction_environment</th>\n",
       "      <th>sex</th>\n",
       "      <th>...</th>\n",
       "      <th>salary_increase</th>\n",
       "      <th>assessment</th>\n",
       "      <th>satisfaction_colleagues</th>\n",
       "      <th>fortnight_hours</th>\n",
       "      <th>action_level</th>\n",
       "      <th>years_experience</th>\n",
       "      <th>num_formations_last_year</th>\n",
       "      <th>years_company</th>\n",
       "      <th>years_since_last_promotion</th>\n",
       "      <th>years_with_current_manager</th>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>id</th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>1.0</th>\n",
       "      <td>41.0</td>\n",
       "      <td>Yes</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Sales</td>\n",
       "      <td>1.0</td>\n",
       "      <td>University</td>\n",
       "      <td>Life Sciences</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Medium</td>\n",
       "      <td>3.0</td>\n",
       "      <td>...</td>\n",
       "      <td>11.0</td>\n",
       "      <td>High</td>\n",
       "      <td>Low</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>8.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>6.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>5.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2.0</th>\n",
       "      <td>49.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Frequently</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>8.0</td>\n",
       "      <td>Secondary</td>\n",
       "      <td>Life Sciences</td>\n",
       "      <td>1.0</td>\n",
       "      <td>High</td>\n",
       "      <td>2.0</td>\n",
       "      <td>...</td>\n",
       "      <td>23.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>80.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>10.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>10.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>7.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4.0</th>\n",
       "      <td>37.0</td>\n",
       "      <td>Yes</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>2.0</td>\n",
       "      <td>Secondary</td>\n",
       "      <td>Other</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>2.0</td>\n",
       "      <td>...</td>\n",
       "      <td>15.0</td>\n",
       "      <td>High</td>\n",
       "      <td>Medium</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>7.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>0.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5.0</th>\n",
       "      <td>33.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Frequently</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>3.0</td>\n",
       "      <td>University</td>\n",
       "      <td>Life Sciences</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>3.0</td>\n",
       "      <td>...</td>\n",
       "      <td>11.0</td>\n",
       "      <td>High</td>\n",
       "      <td>High</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>8.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>8.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>0.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>7.0</th>\n",
       "      <td>27.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>2.0</td>\n",
       "      <td>University</td>\n",
       "      <td>Medical</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Low</td>\n",
       "      <td>3.0</td>\n",
       "      <td>...</td>\n",
       "      <td>12.0</td>\n",
       "      <td>High</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>80.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>6.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>2.0</td>\n",
       "      <td>2.0</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>...</th>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2062.0</th>\n",
       "      <td>39.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>6.0</td>\n",
       "      <td>Secondary</td>\n",
       "      <td>Medical</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>2.0</td>\n",
       "      <td>...</td>\n",
       "      <td>15.0</td>\n",
       "      <td>High</td>\n",
       "      <td>Low</td>\n",
       "      <td>80.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>9.0</td>\n",
       "      <td>5.0</td>\n",
       "      <td>7.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>7.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2064.0</th>\n",
       "      <td>27.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>4.0</td>\n",
       "      <td>Master</td>\n",
       "      <td>Life Sciences</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Medium</td>\n",
       "      <td>4.0</td>\n",
       "      <td>...</td>\n",
       "      <td>20.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>Medium</td>\n",
       "      <td>80.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>6.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>6.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>3.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2065.0</th>\n",
       "      <td>49.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Frequently</td>\n",
       "      <td>Sales</td>\n",
       "      <td>2.0</td>\n",
       "      <td>Secondary</td>\n",
       "      <td>Medical</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>NaN</td>\n",
       "      <td>...</td>\n",
       "      <td>14.0</td>\n",
       "      <td>High</td>\n",
       "      <td>Very_High</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>17.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>9.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>8.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2068.0</th>\n",
       "      <td>34.0</td>\n",
       "      <td>No</td>\n",
       "      <td>Travel_Rarely</td>\n",
       "      <td>Research &amp; Development</td>\n",
       "      <td>8.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>Medical</td>\n",
       "      <td>1.0</td>\n",
       "      <td>Medium</td>\n",
       "      <td>4.0</td>\n",
       "      <td>...</td>\n",
       "      <td>12.0</td>\n",
       "      <td>High</td>\n",
       "      <td>Low</td>\n",
       "      <td>80.0</td>\n",
       "      <td>0.0</td>\n",
       "      <td>6.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>4.0</td>\n",
       "      <td>1.0</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>NaN</th>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>...</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>1471 rows × 29 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "         age turnover             travel              department  distance  \\\n",
       "id                                                                           \n",
       "1.0     41.0      Yes      Travel_Rarely                   Sales       1.0   \n",
       "2.0     49.0       No  Travel_Frequently  Research & Development       8.0   \n",
       "4.0     37.0      Yes      Travel_Rarely  Research & Development       2.0   \n",
       "5.0     33.0       No  Travel_Frequently  Research & Development       3.0   \n",
       "7.0     27.0       No      Travel_Rarely  Research & Development       2.0   \n",
       "...      ...      ...                ...                     ...       ...   \n",
       "2062.0  39.0       No      Travel_Rarely  Research & Development       6.0   \n",
       "2064.0  27.0       No      Travel_Rarely  Research & Development       4.0   \n",
       "2065.0  49.0       No  Travel_Frequently                   Sales       2.0   \n",
       "2068.0  34.0       No      Travel_Rarely  Research & Development       8.0   \n",
       "NaN      NaN      NaN                NaN                     NaN       NaN   \n",
       "\n",
       "         education         career  employee satisfaction_environment  sex  \\\n",
       "id                                                                          \n",
       "1.0     University  Life Sciences       1.0                   Medium  3.0   \n",
       "2.0      Secondary  Life Sciences       1.0                     High  2.0   \n",
       "4.0      Secondary          Other       1.0                Very_High  2.0   \n",
       "5.0     University  Life Sciences       1.0                Very_High  3.0   \n",
       "7.0     University        Medical       1.0                      Low  3.0   \n",
       "...            ...            ...       ...                      ...  ...   \n",
       "2062.0   Secondary        Medical       1.0                Very_High  2.0   \n",
       "2064.0      Master  Life Sciences       1.0                   Medium  4.0   \n",
       "2065.0   Secondary        Medical       1.0                Very_High  NaN   \n",
       "2068.0         NaN        Medical       1.0                   Medium  4.0   \n",
       "NaN            NaN            NaN       NaN                      NaN  NaN   \n",
       "\n",
       "        ... salary_increase  assessment satisfaction_colleagues  \\\n",
       "id      ...                                                       \n",
       "1.0     ...            11.0        High                     Low   \n",
       "2.0     ...            23.0   Very_High               Very_High   \n",
       "4.0     ...            15.0        High                  Medium   \n",
       "5.0     ...            11.0        High                    High   \n",
       "7.0     ...            12.0        High               Very_High   \n",
       "...     ...             ...         ...                     ...   \n",
       "2062.0  ...            15.0        High                     Low   \n",
       "2064.0  ...            20.0   Very_High                  Medium   \n",
       "2065.0  ...            14.0        High               Very_High   \n",
       "2068.0  ...            12.0        High                     Low   \n",
       "NaN     ...             NaN         NaN                     NaN   \n",
       "\n",
       "       fortnight_hours action_level  years_experience  \\\n",
       "id                                                      \n",
       "1.0               80.0          0.0               8.0   \n",
       "2.0               80.0          1.0              10.0   \n",
       "4.0               80.0          0.0               7.0   \n",
       "5.0               80.0          0.0               8.0   \n",
       "7.0               80.0          1.0               6.0   \n",
       "...                ...          ...               ...   \n",
       "2062.0            80.0          1.0               9.0   \n",
       "2064.0            80.0          1.0               6.0   \n",
       "2065.0            80.0          0.0              17.0   \n",
       "2068.0            80.0          0.0               6.0   \n",
       "NaN                NaN          NaN               NaN   \n",
       "\n",
       "        num_formations_last_year years_company years_since_last_promotion  \\\n",
       "id                                                                          \n",
       "1.0                          0.0           6.0                        0.0   \n",
       "2.0                          3.0          10.0                        1.0   \n",
       "4.0                          3.0           0.0                        0.0   \n",
       "5.0                          3.0           8.0                        3.0   \n",
       "7.0                          3.0           2.0                        2.0   \n",
       "...                          ...           ...                        ...   \n",
       "2062.0                       5.0           7.0                        1.0   \n",
       "2064.0                       0.0           6.0                        0.0   \n",
       "2065.0                       3.0           9.0                        0.0   \n",
       "2068.0                       3.0           4.0                        1.0   \n",
       "NaN                          NaN           NaN                        NaN   \n",
       "\n",
       "        years_with_current_manager  \n",
       "id                                  \n",
       "1.0                            5.0  \n",
       "2.0                            7.0  \n",
       "4.0                            0.0  \n",
       "5.0                            0.0  \n",
       "7.0                            2.0  \n",
       "...                            ...  \n",
       "2062.0                         7.0  \n",
       "2064.0                         3.0  \n",
       "2065.0                         8.0  \n",
       "2068.0                         2.0  \n",
       "NaN                            NaN  \n",
       "\n",
       "[1471 rows x 29 columns]"
      ]
     },
     "execution_count": 6,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df  "
   ]
  },
  {
   "cell_type": "markdown",
   "id": "cb34352d",
   "metadata": {
    "papermill": {
     "duration": 0.014359,
     "end_time": "2023-10-05T21:57:11.783951",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.769592",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "### EDA Categorical Variables"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "id": "4c5aca4f",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2023-10-05T21:57:11.817411Z",
     "iopub.status.busy": "2023-10-05T21:57:11.816114Z",
     "iopub.status.idle": "2023-10-05T21:57:11.825947Z",
     "shell.execute_reply": "2023-10-05T21:57:11.824321Z"
    },
    "papermill": {
     "duration": 0.031716,
     "end_time": "2023-10-05T21:57:11.830597",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.798881",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "def graficos_eda_categoricos(cat):\n",
    "    #Calculamos el numero de filas que necesitamos\n",
    "    from math import ceil\n",
    "    filas = ceil(cat.shape[1]/2)\n",
    "    \n",
    "    #Definimos el grafico\n",
    "    f,ax = plt.subplots(nrows = filas, ncols = 2, figsize = (16,filas * 6))\n",
    "    \n",
    "    #Aplanamos para iterar por el grafico como si fuera de 1 dimenson en lugar de 2\n",
    "    ax = ax.flat\n",
    "    \n",
    "    #Creamos el bucle que va anadiendo graficos\n",
    "    for cada, variable in enumerate(cat):\n",
    "        cat [variable].value_counts().plot.barh(ax = ax[cada])\n",
    "        ax[cada].set_title(variable, fontsize = 12,fontweight = \"bold\")\n",
    "        ax[cada].tick_params(labelsize = 12)\n",
    "        \n",
    "    \n",
    "    "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "id": "0ecddc25",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2023-10-05T21:57:11.872926Z",
     "iopub.status.busy": "2023-10-05T21:57:11.871815Z",
     "iopub.status.idle": "2023-10-05T21:57:14.541119Z",
     "shell.execute_reply": "2023-10-05T21:57:14.540288Z"
    },
    "papermill": {
     "duration": 2.69002,
     "end_time": "2023-10-05T21:57:14.545703",
     "exception": false,
     "start_time": "2023-10-05T21:57:11.855683",
     "status": "completed"
    },
    "tags": []
   },
   "outputs": [
    {
     "data": {
      "image/png": "iVBORw0KGgoAAAANSUhEUgAABecAAAzoCAYAAACiVTXDAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjcuMiwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy8pXeV/AAAACXBIWXMAAA9hAAAPYQGoP6dpAAEAAElEQVR4nOzdd5hV1d024GdoQx0QBVFEEFAsqFiiRkHQaBQxagyKBUEsiZpYYoldVOwx1thQXzGWqLEkKjZexZK8xh57SxQLtgihiRRhf3/4ceIwoIBwhnLf13Wua87aa+/z22vG45qHNetUFEVRBAAAAAAAKJs6tV0AAAAAAAAsa4TzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAA8C0qKipSUVGRDh061HYpwFKkXm0XAADMm1GjRmXYsGFJkm7dumWXXXap1XoAAGBemMcCzJlwHgCWEKNGjcppp52WJBk4cKBfagAAWCKYxwLMmW1tAICSL774orZLWCSW1vsCAFhaTZs2LV999VVtlwGwSAnnAWAJ0KtXr2y11Val59dff31p38t99903vXr1Kj0fNWpUqd+pp55aap/1p8RJ0qFDh1L7+++/n5/97Gdp3rx5unbtmiTZd999S8cfeuihnHLKKVlllVXSsGHDbLHFFnnxxRdr1Pj8889nt912S5s2bdKgQYO0adMmffv2zXPPPVfqc+edd5aue/jhh1c7///+7/9Kx3bfffdS+6RJk3Lqqaema9euadSoUaqqqtKrV6/cf//91c4fNWpU6fxevXrl8ccfzw9/+MM0atQov/zlLxdo3AEA+H6+ax77zXnn/fffn6OOOiorrbRSGjZsmA8//DCjR4/Ofvvtl/XXXz8rrLBC6tevn5YtW2brrbfOn//859J1n3/++dJ1dt5552o1jB49OnXq1ElFRUU22WSTUvv06dNzwQUXZKONNkqTJk3SpEmTbLrpprnxxhsX+bgAJLa1AYBl3lZbbZV33nknSbLccsvVOH7wwQeXjidfh+i77LJL3n777dSr9/VU4u67707fvn0zffr0Ur9PP/00d9xxR+6+++7cfvvt2WmnndKnT5+0aNEi48aNy5133pmLLrooFRUVSZLbb7+9dG7//v2TJOPHj0+PHj3y8ssvl45NmTIljz32WB577LFcdtllOeSQQ2rU/Pbbb2e77bbLlClTvs/QAABQRr/61a+qzTuT5IMPPsh1111Xre0///lPRo4cmZEjR+b666/PgAEDsuGGG2attdbK66+/noceeigTJ05Ms2bNkiR33HFHiqJI8t955vTp09O7d+88/PDD1a799NNPZ5999snLL7+cc889d1HdKkASK+cBYIlw6aWX5pJLLik97927d5544ok88cQTOfHEE7/XtT/99NNccMEFeeihh3LCCSfUOP7BBx/k3HPPzZ133pl27dol+XqV+oMPPpjk6y1j9t9//1Iwf/DBB+e+++4rhebTp0/P/vvvny+++CKVlZXp27dvkuTDDz/M3//+99Lr3HHHHUmS5ZdfPr17906SnHjiiaVgfocddsjw4cPzhz/8IW3atEmS/PrXv84HH3xQo+aPPvooq6yySm688cbcd9999jUFAKgl8zOPfeedd3LYYYflgQceyFVXXZVmzZqlTZs2Oeecc3LHHXfkf//3f0uBfKtWrZIkZ5xxRun8vffeO8nXiznuvffeUvusRSB169bNHnvskSS5+OKLS8H8Zpttlrvuuiu33357unTpkiQ577zz8tRTTy3s4QCoxsp5AFgCrLvuuhkzZkzpeevWrdO9e/eFcu0LL7wwBx544FyPH3LIIfnNb36TJHnrrbdy3HHHJUn++c9/JkkeeuihfP7550mSjTbaKJdffnmSr3/xeuqpp/Lcc8/l888/z4gRI7LLLrtk7733zjXXXJPk61+UfvjDH+bpp5/O+++/nyTZbbfdUr9+/cycOTM333xzkqRBgwY58sgjU1lZmaqqquy66665/PLLM23atNx222056qijqtVcp06d3HvvvaVfrgAAqB3zM4/da6+9cvHFF1drW3755dOmTZtcdNFFefnllzN+/PjSKvjk67+YnDBhQqqqqrLXXnvl5JNPTlEUuf3227Pnnnvmk08+yd/+9rckybbbbpvWrVsnSbWta4488sissMIKSb4O+E855ZRSn0033XQhjALAnAnnAWAZ95Of/ORbj/fs2bP09fLLL1/6ety4cUm+Duxnmf2Xl0022aS05/ysfj179ky7du3ywQcf5I477sjvfve7OW5p8/nnn+c///lPkq8/EGybbbaZY32vv/56jbbVV19dMA8AsISZ07z0wgsvzJFHHvmt540bNy5VVVVZbbXVsvnmm+dvf/tbHnjggXzxxRe58847M3PmzCT/nWcm1eew3/y8o2+a0zwTYGGyrQ0ALAVm7dueJDNmzCh9PWtF+7dZccUVv/X4N/ehn7XHfJJqK5bmpa5vtu21115Jkvfeey/PPPNMaUubWb9QzY8vvviiRtt33RMAAIufOc3hLr300tLXv/nNb/Lwww/niSeeyLrrrltqnxW+J/8N4CdPnpz77ruvtAikSZMm873V4ZzmmQALk3AeAJYQder893/b3/wFJEmaN29e+vqTTz4p9RkxYsR3XndOAfr8WGONNUpfP/3009WOffP5N/vN2g80+Xpf+Vkf/LXXXnuV6llhhRVK/zDQtGnTTJw4MUVRVHvMmDGjxgeELYx7AgBg4fm2eew3zWkON3r06CRf/wXnueeem6233jobbLBBqX12s7ZITJIrrrgijz/+eJJkl112SZMmTUr9vjk3feedd2rMM4uiqPFhsQALm3AeAJYQ31zB/te//jX3339//vrXv+azzz5L586dS8cOPfTQXH755dlxxx2r/bnuovLjH/+4tN3Ns88+m1/96le5//77c+ihh+bZZ59N8nXQvu2225bOWXfddbPeeuslSbV/QPjmnxrXqVMne+65Z5Jk0qRJ+fGPf5xbbrkl//u//5thw4bl6KOPTufOnat9qCwAAIufb5vHfpf27dsnScaMGZNzzjkn9913X3bdddeMHTt2jv2XX3759O7dO0kycuTI0l+VfnOemVRfLLLjjjvm+uuvz8MPP5wbb7wxJ510UtZdd93cdttt83ejAPPJnvMAsIRYa6210qZNm3zyySd59913s8MOOyRJrrvuuuy///658MILM3PmzLzwwgv55S9/mSRZc80188YbbyzSupo0aZJrr702u+22W6ZPn57LLrssl112Wel4/fr1c+2111ZbqZR8/QvRSy+9VHq+4YYbZs0116zW58wzz8wTTzyRl19+OU8++WSefPLJRXovAAAsfN82j/0uP//5z3PMMcckSY4//vgkXy/86NKlS9588805nrP33nvn7rvvLj1v3bp1jc8vOvzww/Pggw/m4YcfzmuvvZZ99913QW4N4Huxch4AlhD16tXL3Xffne7du6dZs2bVjq211lq56aab0rlz5zRo0CBdu3bNbbfdln79+pWltp133jlPPvlk+vbtm9atW6devXpp1apVdt111/zf//1fdtpppxrn7LXXXtX+xHn21UxJ0qJFizz55JMZMmRI1l9//TRq1CiNGzfO6quvnr59++aPf/xjNttss0V6bwAAfD/fNo/9Lr/+9a9zxhlnpH379mncuHF69eqVRx55JG3atJnrOTvttFOqqqpKz/fYY49qn52UJA0aNMgDDzyQSy65JJtsskmaNWuWhg0bZrXVVkufPn1y7bXX5qc//en83SjAfKoo5uXT3AAAAAAAgIXGynkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJnVq+0CgEVv5syZ+eijj9KsWbNUVFTUdjkAAPOtKIpMnDgxK6+8curUscZoSWM+CgAs6RbFfFQ4D8uAjz76KO3atavtMgAAvrcPPvggq6yySm2XwXwyHwUAlhYLcz4qnIdlQLNmzZJ8/eZRVVVVy9UAAMy/CRMmpF27dqV5DUsW81EAYEm3KOajwnlYBsz60+Gqqiq/DAEASzRboiyZzEcBgKXFwpyP2qwRAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBm9Wq7AAAAAJYNXQc/mDqVjWu7jCXKqHP61HYJAMAiYuU8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKLN6tV0AUD5dBz+YOpWNa7sMZjPqnD61XQIAAAAAZWblPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAA86WioiKnnnpqbZcBALBEE84DAADLjGHDhqWioiINGzbM6NGjaxzv1atXunbtWpZaTj311FRUVHzno1evXmWpBwCA8qpX2wUAAACU29SpU3POOefk0ksvrbUadt1113Tu3Ln0fNKkSTn44IPz05/+NLvuumupfcUVV6yN8gAAWMSE8wAAwDKnW7duufrqq3P88cdn5ZVXrpUa1ltvvay33nql559//nkOPvjgrLfeeunfv/9cz5syZUoaNGiQOnX8ITQAwJLMbA4AAFjmnHDCCZkxY0bOOeecb+331VdfZciQIenUqVMqKyvToUOHnHDCCZk6dWq1fh06dMiOO+6Yv/71r9lkk03SsGHDdOzYMX/4wx++V52PPvpoKioqcsstt+Skk05K27Zt07hx40yYMCFjx47N0UcfnXXXXTdNmzZNVVVVevfunRdffLF0/qeffpp69erltNNOq3HtN998MxUVFfn9739fahs3blyOOOKItGvXLpWVlencuXPOPffczJw583vdBwAANQnnAQCAZc5qq62WAQMG5Oqrr85HH300134HHHBATjnllGy44Ya58MIL07Nnz5x99tnZY489avT95z//mb59+2bbbbfN7373uyy33HLZd9998+qrr37veocMGZLhw4fn6KOPzllnnZUGDRrknXfeyZ///OfsuOOOueCCC3LMMcfk5ZdfTs+ePUv3tOKKK6Znz5657bbbalzz1ltvTd26dbPbbrslSSZPnpyePXvmxhtvzIABA3LJJZdkiy22yPHHH58jjzzye98DAADV2dYGAABYJp144on5wx/+kHPPPTcXX3xxjeMvvvhirr/++hxwwAG5+uqrkySHHHJIWrdunfPPPz8jR47MVlttVer/5ptv5vHHH0+PHj2SJLvvvnvatWuX6667Lueff/73qnXKlCl59tln06hRo1Lbuuuum7feeqva9jb77LNP1lxzzVx77bU5+eSTkyT9+vXLL37xi7zyyivVPuz21ltvTc+ePUt72l9wwQX517/+lRdeeCGrr756kuQXv/hFVl555fz2t7/NUUcdlXbt2s1TvVOnTq321wUTJkxY8JsHAFhKWTkPAAAskzp27Jh99tknQ4cOzccff1zj+H333ZckNVaNH3XUUUmS4cOHV2tfe+21S8F8krRq1SpdunTJO++8871rHThwYLVgPkkqKytLwfyMGTMyZsyYNG3aNF26dMnzzz9f6rfrrrumXr16ufXWW0ttr7zySl577bX069ev1PanP/0pPXr0yHLLLZfPP/+89Nhmm20yY8aMPP744/Nc79lnn53mzZuXHvMa6gMALEuE8wAAwDLrpJNOyldffTXHveffe++91KlTJ507d67W3qZNm7Ro0SLvvfdetfZVV121xjWWW265/Oc//0nydYD+ySefVHtMmzZtnupcbbXVarTNnDkzF154YVZfffVUVlZmhRVWSKtWrfLSSy9l/PjxpX4rrLBCfvSjH1Xb2ubWW29NvXr1suuuu5ba3n777TzwwANp1apVtcc222yTJPnss8/mqdYkOf744zN+/PjS44MPPpjncwEAlhW2tQEAAJZZHTt2TP/+/TN06NAcd9xxc+xTUVExT9eqW7fuHNuLokiSfPDBBzVC9pEjR6ZXr17fee3ZV80nyVlnnZWTTz45++23X4YMGZKWLVumTp06OeKII2p8gOsee+yRQYMG5R//+Ee6deuW2267LT/60Y+ywgorlPrMnDkz2267bX7zm9/MsYY11ljjO+ucpbKyMpWVlfPcHwBgWSScBwAAlmknnXRSbrzxxpx77rnV2tu3b5+ZM2fm7bffzlprrVVq//TTTzNu3Li0b99+vl6nTZs2GTFiRLW29ddff4Hrvv3227PVVlvl2muvrdY+bty4aqF7kuyyyy75xS9+Udra5q233srxxx9frU+nTp0yadKk0kp5AAAWLdvaAAAAy7ROnTqlf//+ueqqq/LJJ5+U2nfYYYckyUUXXVSt/wUXXJAk6dOnz3y9TsOGDbPNNttUeyy33HILXHfdunVLq/Jn+dOf/pTRo0fX6NuiRYtst912ue2223LLLbekQYMG2WWXXar12X333fPkk0/mwQcfrHH+uHHj8tVXXy1wrQAA1GTlPAAAsMw78cQTc8MNN+TNN9/MOuusk+TrVe0DBw7M0KFDM27cuPTs2TNPP/10rr/++uyyyy7ZaqutarXmHXfcMaeffnoGDRqUzTffPC+//HJuuummdOzYcY79+/Xrl/79++fyyy/PdtttlxYtWlQ7fswxx+Tuu+/OjjvumH333TcbbbRRvvjii7z88su5/fbbM2rUqBor8gEAWHDCeQAAYJnXuXPn9O/fP9dff3219muuuSYdO3bMsGHDctddd6VNmzY5/vjjM3jw4Fqq9L9OOOGEfPHFF7n55ptz6623ZsMNN8zw4cPnunf+TjvtlEaNGmXixInp169fjeONGzfOY489lrPOOit/+tOf8oc//CFVVVVZY401ctppp6V58+aL+pYAAJYpFcXsfwcJLHUmTJiQ5s2bp90Rt6VOZePaLofZjDpn/v4kHgCWRbPmM+PHj09VVVVtl8N8Mh9dcOaKALB4WBTzUXvOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeVhEevfuneWWWy6ffvppjWPjx4/PSiutlE033TQzZ86sheoAAAAAgNoknIdF5PLLL8+0adPy61//usaxE044IZ9//nmGDh2aOnX8ZwgAAAAAyxqpICwiq622WgYPHpw//vGPeeihh0rtzzzzTK688soceeSRWX/99WuxQgAAAACgtgjnYRE68sgjs9566+WQQw7JlClTMmPGjBx00EFp3759Bg8enDfeeCN9+/ZNy5Yt07Bhw2y88ca5++67q11j+vTpOe2007L66qunYcOGWX755dO9e/eMGDGilu4KAAAAAPi+6tV2AbA0q1evXoYOHZrNN988Q4YMSevWrfP888/ngQceyLvvvpstttgibdu2zXHHHZcmTZrktttuyy677JI77rgjP/3pT5Mkp556as4+++wccMAB2WSTTTJhwoQ8++yzef7557PtttvW8h0CAAAAAAtCOA+L2KabbppDDjkkv/3tb1NZWZk999wz2223XbbZZpusuuqqeeaZZ1JZWZkkOeSQQ9K9e/cce+yxpXB++PDh2WGHHTJ06NB5fs2pU6dm6tSppecTJkxYuDcFAAAAAHwvwnkogzPPPDO33357Jk+enAsvvDBjx47NI488ktNPPz0TJ07MxIkTS3232267DB48OKNHj07btm3TokWLvPrqq3n77bez+uqrz9PrnX322TnttNMW1e0AAMACeeW07VJVVVXbZQAALBbsOQ9lUFVVlS5duqRdu3ZZccUV889//jNFUeTkk09Oq1atqj0GDx6cJPnss8+SJKeffnrGjRuXNdZYI+uuu26OOeaYvPTSS9/6escff3zGjx9fenzwwQeL/B4BAAAAgHln5TzUgpkzZyZJjj766Gy33XZz7NO5c+ckyZZbbpl//etf+ctf/pKHHnoo11xzTS688MJceeWVOeCAA+Z4bmVlZWmrHAAAAABg8SOch1rQsWPHJEn9+vWzzTbbfGf/li1bZtCgQRk0aFAmTZqULbfcMqeeeupcw3kAAAAAYPFmWxuoBa1bt06vXr1y1VVX5eOPP65x/N///nfp6zFjxlQ71rRp03Tu3LnaB74CAAAAAEsWK+ehllx22WXp3r171l133Rx44IHp2LFjPv300zz55JP58MMP8+KLLyZJ1l577fTq1SsbbbRRWrZsmWeffTa33357fvWrX9XyHQAAAAAAC0o4D7Vk7bXXzrPPPpvTTjstw4YNy5gxY9K6detssMEGOeWUU0r9DjvssNx999156KGHMnXq1LRv3z5nnHFGjjnmmFqsHgAAAAD4PiqKoihquwhg0ZowYUKaN2+edkfcljqVjWu7HGYz6pw+tV0CACz2Zs1nxo8fn6qqqtouh/nk+wcALOkWxXzGnvMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZvVquwCgfF45bbtUVVXVdhkAAAAAsMyzch4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUWb3aLgAAAIBlQ9fBD6ZOZePaLoMlzKhz+tR2CQCwSFg5DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnn4Ru++uqrnH766fnwww9ruxQAAAAAYCkmnIdvqFevXn7729/mq6++qu1SAAAAAIClmHAeZrP11lvnscceq+0yAAAAAIClWL3aLgAWN717985xxx2Xl19+ORtttFGaNGlS7fhOO+1US5UBAAAAAEsL4TzM5pBDDkmSXHDBBTWOVVRUZMaMGeUuCQAAAABYygjnYTYzZ86s7RIAAAAAgKWcPefhW0yZMqW2SwAAAAAAlkLCeZjNjBkzMmTIkLRt2zZNmzbNO++8kyQ5+eSTc+2119ZydQAAAADA0kA4D7M588wzM2zYsJx33nlp0KBBqb1r16655pprarEyAAAAAGBpIZyH2fzhD3/I0KFDs/fee6du3bql9vXXXz9vvPFGLVYGAAAAACwthPMwm9GjR6dz58412mfOnJnp06fXQkUAAAAAwNKmXm0XAIubtddeO0888UTat29frf3222/PBhtsUEtVAQB87aWXXprnvuutt94irAQAAPg+hPMwm1NOOSUDBw7M6NGjM3PmzNx55515880384c//CH33ntvbZcHACzjunXrloqKihRFMcfjs45VVFRkxowZZa4OAACYV8J5mM3OO++ce+65J6effnqaNGmSU045JRtuuGHuueeebLvttrVdHgCwjHv33XdruwQAAGAhEM7DHPTo0SMjRoyo7TIAAGqYfes9AABgyeQDYWE2BxxwQB599NHaLgMAYJ7ccMMN2WKLLbLyyivnvffeS5JcdNFF+ctf/lLLlQEAAN9GOA+z+fe//53tt98+7dq1yzHHHJN//OMftV0SAMAcXXHFFTnyyCOzww47ZNy4caU95lu0aJGLLrqodosDAAC+lXAeZvOXv/wlH3/8cU4++eQ888wz2WijjbLOOuvkrLPOyqhRo2q7PACAkksvvTRXX311TjzxxNStW7fUvvHGG+fll1+uxcoAAIDvIpyHOVhuueXy85//PI8++mjee++97LvvvrnhhhvSuXPn2i4NAKDk3XffzQYbbFCjvbKyMl988UUtVAQAAMwr4Tx8i+nTp+fZZ5/NU089lVGjRmXFFVes7ZIAAEpWW221OW7B98ADD2SttdYqf0EAAMA8q1fbBcDiaOTIkbn55ptzxx13ZObMmdl1111z7733Zuutt67t0gAASo488sj88pe/zJQpU1IURZ5++un88Y9/zNlnn51rrrmmtssDAAC+hXAeZtO2bduMHTs222+/fYYOHZqf/OQnqaysrO2yAABqOOCAA9KoUaOcdNJJmTx5cvbaa6+svPLKufjii7PHHnvUdnkAAMC3sK0NzObUU0/Nxx9/nLvuuit9+/YVzAMAi7W99947b7/9diZNmpRPPvkkH374Yfbff//aLmuRO/XUU1NRUVHbZSx1Hn300VRUVOTRRx+t7VIAAJZ6wnmYzYEHHpgWLVokST788MN8+OGHtVsQAMBcnHHGGXn33XeTJI0bN07r1q3n+xoVFRXz9FgawtpZgf6cHldeeWVtl1dWl19+eYYNG1bbZQAALNNsawOzmTlzZs4444z87ne/y6RJk5IkzZo1y1FHHZUTTzwxder4Ny0AYPHwpz/9KYMHD86mm26a/v37Z/fdd88KK6wwX9e44YYbqj3/wx/+kBEjRtRoX5o+YPaKK65I06ZNq7VtuummtVRN7bj88suzwgorZN99963tUgAAllnCeZjNiSeemGuvvTbnnHNOtthiiyTJX//615x66qmZMmVKzjzzzFquEADgay+++GJeffXV3HTTTTn//PNzxBFHZNttt83ee++dXXbZJY0bN/7Oa/Tv37/a87///e8ZMWJEjfbZTZ48eZ6uvzjq27fvPP8jxhdffJEmTZos4ooAAFgWWQIMs7n++utzzTXX5OCDD856662X9dZbL4ccckiuvvpqf/oLACx21llnnZx11ll55513MnLkyHTo0CFHHHFE2rRps9Beo1evXunatWuee+65bLnllmncuHFOOOGEJMlf/vKX9OnTJyuvvHIqKyvTqVOnDBkyJDNmzCid/6tf/SpNmzbN5MmTa1x7zz33TJs2bar1v//++9OjR480adIkzZo1S58+ffL6668vtPuZm2HDhqWioiKPPfZYDjnkkLRu3TqrrLLKt9b16quv1rjOn//853Tt2jUNGzZM165dc9ddd2XfffdNhw4dSn3mtrf7qFGjUlFRUWPe+cYbb6Rv375p2bJlGjZsmI033jh33333HOv/29/+liOPPDKtWrVKkyZN8tOf/jT//ve/S/06dOiQV199NY899lhpW59evXrNcUwGDx6c+vXrVzt/lp///Odp0aJFpkyZMpcRBQDg2wjnYTZjx47NmmuuWaN9zTXXzNixY2uhIgCAedOkSZM0atQoDRo0yPTp0xfqtceMGZPevXunW7duueiii7LVVlsl+ToQbtq0aY488shcfPHF2WijjXLKKafkuOOOK53br1+/fPHFFxk+fHi1a06ePDn33HNP+vbtm7p16yb5epudPn36pGnTpjn33HNz8skn57XXXst222230O5l7Nix+fzzz0uP//znP9WOH3LIIXnttdeq3cfc6urevXtGjRpVOvehhx7Kz372s1RUVOTss8/OLrvskkGDBuXZZ59d4HpfffXVbLbZZnn99ddz3HHH5Xe/+12aNGmSXXbZJXfddVeN/oceemhefPHFDB48OAcffHDuueee/OpXvyodv+iii7LKKqtkzTXXzA033JAbbrghJ5544hxfe5999slXX32VW2+9tVr7tGnTcvvtt+dnP/tZGjZsWOO8qVOnZsKECdUeAABUZ1sbmM3666+f3//+97nkkkuqtf/+97/P+uuvX0tVAQDM2bvvvpubb745N998c95888307Nkzp512Wvr27btQX+eTTz7JlVdemV/84hfV2m+++eY0atSo9Pyggw7KQQcdlMsvvzxnnHFGKisr071797Rt2za33nprdtttt1Lf4cOH54svvki/fv2SJJMmTcphhx2WAw44IEOHDi31GzhwYLp06bLQ7mX2a7Vv375awN6yZcs8/PDDpX8w+K66zjrrrFL7sccemxVXXDF//etf07x58yRJz5498+Mf/zjt27dfoHoPP/zwrLrqqnnmmWdSWVmZ5Ot/QOjevXuOPfbY/PSnP63Wf/nll89DDz2UioqKJF9/ptIll1yS8ePHp3nz5tlll11y0kknZYUVVvjO7Ys6d+6cH/7wh7nxxhurBfzDhw/Pf/7zn+yzzz5zPO/ss8/OaaedtkD3CwCwrLByHmZz3nnn5X/+53+y9tprZ//998/++++ftddeO8OGDctvf/vb2i4PAKBks802S+fOnXP77bdn0KBBee+99/Lwww9n//33LwXDC0tlZWUGDRpUo/2bwfzEiRPz+eefp0ePHpk8eXLeeOONJElFRUV222233HfffZk0aVKp/6233pq2bdume/fuSZIRI0Zk3Lhx2XPPPautbK9bt2422mijhXYvd9xxR0aMGFF63HTTTdWOH3jggaVg/rvq2nTTTTNy5Mgkyccff5x//OMfGThwYLXx33bbbbP22msvUK1jx47NI488kt133700vp9//nnGjBmT7bbbLm+//XZGjx5d7Zyf//znpWA+SXr06JEZM2bkvffeW6AaBgwYkKeeeir/+te/Sm033XRT2rVrl549e87xnOOPPz7jx48vPT744IMFem0AgKWZlfMwm549e+att97KZZddVvqFctddd80hhxySlVdeuZarAwD4rx/96EelRQWLWtu2bdOgQYMa7a+++mpOOumkPPLIIzW2Lhk/fnzp6379+uWiiy7K3Xffnb322iuTJk3Kfffdl1/84helIPntt99Okmy99daL8E6SLbfc8ls/EHa11Var9vy76qqqqkqSUvi9+uqr1+jTpUuXPP/88/Nd6z//+c8URZGTTz45J5988hz7fPbZZ2nbtm3p+aqrrlrt+HLLLZckNbbvmVf9+vXLEUcckZtuuimnnHJKxo8fn3vvvTe//vWvq/0jwDdVVlaWVvkDADBnwnmYg5VXXjlnnnlmbZcBAPCtyjlf+eYK+VnGjRuXnj17pqqqKqeffno6deqUhg0b5vnnn8+xxx6bmTNnlvputtlm6dChQ2677bbstddeueeee/Lll1+WtrRJUup/ww031PhA2y+++CK77LLLorm52cx+r99WV5LUqzf/v1bNLdT+5gfjfvO1jz766Lnuu9+5c+dqz7+56v+biqKY3zKTfB3u77jjjqVw/vbbb8/UqVO/c0scAAC+nXAe5mDcuHF5+umn89lnn1X7pTL5+s96AQAWFx9++GHuvvvuvP/++5k2bVq1YxdccMEife1HH300Y8aMyZ133pktt9yy1P7uu+/Osf/uu++eiy++OBMmTMitt96aDh06ZLPNNisd79SpU5KkdevW2WabbaqdW5sfKPptdX3TrD3lZ620/6Y333yz2vNZq9nHjRtXrX32rWc6duyYJKlfv/63vvb8mts/DszNgAEDsvPOO+eZZ57JTTfdlA022CDrrLPOQqsHAGBZJJyH2dxzzz3Ze++9M2nSpFRVVVX7xaWiokI4DwAsNh5++OHstNNO6dixY95444107do1o0aNSlEU2XDDDRf5689aof3NFdnTpk3L5ZdfPsf+/fr1y3nnnZfrr78+DzzwQA4//PBqx7fbbrtUVVXlrLPOylZbbZX69esvuuLnw3fV9e9//zutWrXKSiutlG7duuX666/PcccdV9p3fsSIEXnttdeqfSBs+/btU7du3Tz++OPV/iJg9rFr3bp1evXqlauuuiqHHnpoVlpppTm+9vxq0qRJjX8Y+Da9e/fOCiuskHPPPTePPfaYz2ICAFgIhPMwm6OOOir77bdfzjrrrDRu3Li2ywEAmKvjjz8+Rx99dE477bQ0a9Ysd9xxR1q3bp29994722+//SJ//c033zzLLbdcBg4cmMMOOywVFRW54YYb5rp9yoYbbpjOnTvnxBNPzNSpU6ttaZN8vXf7FVdckX322Scbbrhh9thjj7Rq1Srvv/9+7r777kV+P3PzbXUNHz48W2yxRX7/+98nSc4+++z06dMn3bt3z3777ZexY8fm0ksvzTrrrFPtw3CbN2+e3XbbLZdeemkqKirSqVOn3Hvvvfnss89qvP5ll12W7t27Z911182BBx6Yjh075tNPP82TTz6ZDz/8MC+++OJ839NGG22UK664ImeccUY6d+6c1q1bf+te//Xr188ee+yR3//+96lbt2723HPP+X5NAACqq1PbBcDiZvTo0TnssMME8wDAYu/1118v/VVfvXr18uWXX6Zp06Y5/fTTc+655y7y119++eVz7733ZqWVVspJJ52U888/P9tuu23OO++8uZ7Tr1+/TJw4MZ07d57j6v699torDz/8cNq2bZvf/va3Ofzww3PLLbdkvfXWW5S38p3mVle3bt0yaNCgUr/tt98+f/rTnzJjxowcf/zxufPOO3Pddddl4403rnHNSy+9NDvvvHOuvPLKnHTSSVl11VVz/fXX1+i39tpr59lnn02fPn0ybNiw/PKXv8yVV16ZOnXq5JRTTlmg+znllFOyww475Lzzzsuee+6Z008//TvPmfWz9qMf/ajGCn4AAOZfRbGgnwoES6ldd901e+yxR3bffffaLmWhmTBhQpo3b57x48enqqqqtssBABaSNm3aZOTIkVlrrbWy9tpr55xzzslOO+2UF198MVtssUW1ldpLuiV9PrPvvvvm0UcfzahRo2q7lAX24osvplu3bvnDH/6QffbZZ77OnfX9a3fEbalTaREM82fUOX1quwQAWCTzUdvawGz69OmTY445Jq+99lrWXXfdGnuK7rTTTrVUGQBAdZtttln++te/Zq211soOO+yQo446Ki+//HLuvPPOah+0CgvD1VdfnaZNm2bXXXet7VIAAJYKwnmYzYEHHpgkc/zT3oqKisyYMaPcJQEAzNEFF1xQWh1/2mmnZdKkSbn11luz+uqr54ILLqjl6spn/Pjx+fLLL7+1T5s2bcpUzdLnnnvuyWuvvZahQ4fmV7/6VZo0aVLbJQEALBWE8zCbmTNn1nYJAADfacaMGfnwww9Le7E3adIkV155ZS1XVTsOP/zwOe7V/k1281xwhx56aD799NPssMMOOe2002q7HACApYZwHr5h+vTpadSoUf7xj3+ka9eutV0OAMBc1a1bNz/+8Y/z+uuvp0WLFrVdTq36zW9+k/79+9d2Gd9q2LBhtV3CAluS98kHAFicCefhG+rXr59VV13V1jUAwBKha9eueeedd7LaaqvVdim1au21187aa69d22UAAMB8qVPbBcDi5sQTT8wJJ5yQsWPH1nYpAADf6owzzsjRRx+de++9Nx9//HEmTJhQ7QEAACy+rJyH2fz+97/PP//5z6y88spp3759jQ+8ev7552upMgCA6nbYYYckyU477ZSKiopSe1EUPsgeAAAWc8J5mM0uu+xS2yUAAMyT6667Lu3atUvdunWrtc+cOTPvv/9+LVUFAADMC+E8zGbw4MG1XQIAwDzZb7/98vHHH6d169bV2seMGZNtttkmAwcOrKXKAACA72LPeQAAWELN2r5mdpMmTUrDhg1roSIAAGBeWTkPs6lTp84cf8mdxd6tAEBtO/LII5MkFRUVOfnkk9O4cePSsRkzZuSpp55Kt27daqk6AABgXgjnYTZ33XVXtefTp0/PCy+8kOuvvz6nnXZaLVUFAPBfL7zwQpKvV86//PLLadCgQelYgwYNsv766+foo4+urfIAAIB5IJyH2ey888412vr27Zt11lknt956a/bff/9aqAoA4L9GjhyZJBk0aFAuvvjiVFVV1XJFAADA/LLnPMyjzTbbLA8//HBtlwEAUHLdddcJ5gEAYAklnId58OWXX+aSSy5J27Zta7sUAAAAAGApYFsbmM1yyy1X7QNhi6LIxIkT07hx49x44421WBkAAAAAsLQQzsNsLrroosyYMSN169ZNktSpUyetWrXKpptumokTJ9ZydQAAAADA0kA4D7PZb7/98vHHH6d169bV2seMGZPVVlstM2bMqKXKAAAAAIClhT3nYTZFUVTb1maWSZMmpWHDhrVQEQAAAACwtLFyHv6/I488MklSUVGRk08+OY0bNy4dmzFjRp566ql069atlqoDAAAAAJYmwnn4/1544YUkX6+cf/nll9OgQYPSsQYNGmT99dfP0UcfXVvlAQAAAABLEeE8/H8jR45MkgwaNCgXX3xxqqqqarkiAAAAAGBpJZyH2Vx33XW1XQIAAAAAsJTzgbAAAAAAAFBmVs4DAABQFq+ctp3tIwEA/j8r5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZ1avtAoDy6Tr4wdSpbFzbZQAAS5FR5/Sp7RIAAGCJZOU8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4D2U0bNiwVFRUpGHDhhk9enSN47169UrXrl1roTIAAAAAoJyE81ALpk6dmnPOOae2ywAAAAAAaolwHmpBt27dcvXVV+ejjz6q7VIAAAAAgFognIdacMIJJ2TGjBnfuXr+q6++ypAhQ9KpU6dUVlamQ4cOOeGEEzJ16tQyVQoAAAAALArCeagFq622WgYMGPCdq+cPOOCAnHLKKdlwww1z4YUXpmfPnjn77LOzxx57lLFaAAAAAGBhE85DLTnxxBPz1Vdf5dxzz53j8RdffDHXX399DjjggPzpT3/KIYcckuuvvz5HH310/vznP2fkyJFzvfbUqVMzYcKEag8AAAAAYPFRr7YLgGVVx44ds88++2To0KE57rjjstJKK1U7ft999yVJjjzyyGrtRx11VM4///wMHz48W2211RyvffbZZ+e0005bNIUDAMAC6jr4wdSpbFzbZQAAS5FR5/Sp7RIWmJXzUItOOumkfPXVV3Pce/69995LnTp10rlz52rtbdq0SYsWLfLee+/N9brHH398xo8fX3p88MEHC712AAAAAGDBCeehFnXs2DH9+/fP0KFD8/HHH8+xT0VFxXxft7KyMlVVVdUeAAAAAMDiQzgPtWzW6vnZ955v3759Zs6cmbfffrta+6effppx48alffv25SwTAAAAAFiIhPNQyzp16pT+/fvnqquuyieffFJq32GHHZIkF110UbX+F1xwQZKkT58ldz8tAAAAAFjW+UBYWAyceOKJueGGG/Lmm29mnXXWSZKsv/76GThwYIYOHZpx48alZ8+eefrpp3P99ddnl112meuHwQIAAAAAiz8r52Ex0Llz5/Tv379G+zXXXJPTTjstzzzzTI444og88sgjOf7443PLLbfUQpUAAAAAwMJSURRFUdtFAIvWhAkT0rx587Q74rbUqWxc2+UAAEuRUeeUZ6u9WfOZ8ePH+7D7JZD5KACwqCzJ81Er5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAIDv4dRTT01FRUVtl7FQDBs2LBUVFRk1alRtlwIAsNQTzgMAAIuFioqKuT6aN2+eJGnevHkeffTR2i10IZgV6M961K9fPx06dMhhhx2WcePG1XZ5AACUQb3aLgAAACBJbrjhhmrP//CHP2TEiBG54YYb8uWXX+bnP/95hg4dmrXWWquWKlz4rrjiijRt2jRffPFFHn744Vx66aV5/vnn89e//rW2SwMAYBETzgMAAIuF/v37V3v+97//PSNGjEj//v0zYcKE/PznP0+/fv1SVVVVrd/kyZPTuHHjcpa60PTt2zcrrLBCkuQXv/hF9thjj9x66615+umns8kmm3zv60+ZMiUNGjRInTr+aBoAYHFjhgYAACwx+vTpk65du+a5557LlltumcaNG+eEE05IkvzlL39Jnz59svLKK6eysjKdOnXKkCFDMmPGjNL5v/rVr9K0adNMnjy5xrX33HPPtGnTplr/+++/Pz169EiTJk3SrFmz9OnTJ6+++uoiu78ePXokSf71r3+V2saOHZujjz466667bpo2bZqqqqr07t07L774YrVzH3300VRUVOSWW27JSSedlLZt26Zx48aZMGFCkuSpp57K9ttvn+bNm6dx48bp2bNn/va3v31rPQMHDswKK6yQ6dOn1zj24x//OF26dPm+twwAsMwSzgMAAEuUMWPGpHfv3unWrVsuuuiibLXVVkm+/jDTpk2b5sgjj8zFF1+cjTbaKKecckqOO+640rn9+vXLF198keHDh1e75uTJk3PPPfekb9++qVu3bpKvt9np06dPmjZtmnPPPTcnn3xyXnvttXTv3n2RfWDqrOsut9xypbZ33nknf/7zn7PjjjvmggsuyDHHHJOXX345PXv2zEcffVTjGkOGDMnw4cNz9NFH56yzzkqDBg3yyCOPZMstt8yECRMyePDgnHXWWRk3bly23nrrPP3003OtZ5999smYMWPy4IMPVmv/5JNP8sgjj9T4awcAAOadbW0AAIAlyieffJIrr7wyv/jFL6q133zzzWnUqFHp+UEHHZSDDjool19+ec4444xUVlame/fuadu2bW699dbstttupb7Dhw/PF198kX79+iVJJk2alMMOOywHHHBAhg4dWuo3cODAdOnSJWeddVa19gU1duzYJMkXX3yRRx55JJdddllatWqVLbfcstRn3XXXzVtvvVVta5p99tkna665Zq699tqcfPLJ1a45ZcqUPPvss6WxKIoiBx10ULbaaqvcf//9qaioSPL1NjrrrLNOTjrppDz00ENzrG/rrbfOKquskhtvvDE77rhjqf2Pf/xjZs6cOddwfurUqZk6dWrp+azV+wAA/JeV8wAAwBKlsrIygwYNqtH+zWB+4sSJ+fzzz9OjR49Mnjw5b7zxRpKkoqIiu+22W+67775MmjSp1P/WW29N27Zt07179yTJiBEjMm7cuOy55575/PPPS4+6detm0003zciRIxfKvXTp0iWtWrVKhw4dst9++6Vz5865//77q+2hX1lZWQrmZ8yYkTFjxqRp06bp0qVLnn/++RrXHDhwYLWx+Mc//pG33347e+21V8aMGVO6ly+++CI/+tGP8vjjj2fmzJlzrK9OnTrZe++9c/fdd2fixIml9ptuuimbb755VltttTmed/bZZ6d58+alR7t27RZofAAAlmbCeQAAYInStm3bNGjQoEb7q6++mp/+9Kdp3rx5qqqq0qpVq9LK7vHjx5f69evXL19++WXuvvvuJF+vkr/vvvuy2267lVaVv/3220m+XjneqlWrao+HHnoon3322UK5lzvuuCMjRozIzTffnM022yyfffZZtWA9SWbOnJkLL7wwq6++eiorK7PCCiukVatWeemll6rd1yyzB+az7mXgwIE17uWaa67J1KlT53idWQYMGJAvv/wyd911V5LkzTffzHPPPZd99tlnruccf/zxGT9+fOnxwQcfzPOYAAAsK2xrAwAALFFmD6+TZNy4cenZs2eqqqpy+umnp1OnTmnYsGGef/75HHvssdVWhm+22Wbp0KFDbrvttuy1116555578uWXX5a2tElS6n/DDTekTZs2NV6vXr2F86vUlltumRVWWCFJ8pOf/CTrrrtu9t577zz33HOl1fJnnXVWTj755Oy3334ZMmRIWrZsmTp16uSII46Y44r3OYX7SfLb3/423bp1m2MdTZs2nWuNa6+9djbaaKPceOONGTBgQG688cY0aNAgu++++1zPqaysTGVl5bfeOwDAsk44DwAALPEeffTRjBkzJnfeeWe1/drffffdOfbffffdc/HFF2fChAm59dZb06FDh2y22Wal4506dUqStG7dOttss82iLf7/a9q0aQYPHpxBgwbltttuyx577JEkuf3227PVVlvl2muvrdZ/3LhxpWD/28y6l6qqqgW+lwEDBuTII4/Mxx9/nJtvvjl9+vSp9qG1AADMP9vaAAAAS7y6desm+frDT2eZNm1aLr/88jn279evX6ZOnZrrr78+DzzwQI1V4Nttt12qqqpy1llnZfr06TXO//e//70Qq/+vvffeO6usskrOPffcUlvdunWr3VeS/OlPf8ro0aPn6ZobbbRROnXqlPPPP7/aPvuzzMu97LnnnqmoqMjhhx+ed955Z64fBAsAwLyzch4AAFjibb755lluueUycODAHHbYYamoqMgNN9xQI9SeZcMNN0znzp1z4oknZurUqdW2tEm+XmV+xRVXZJ999smGG26YPfbYI61atcr777+f4cOHZ4sttsjvf//7hX4f9evXz+GHH55jjjkmDzzwQLbffvvsuOOOOf300zNo0KBsvvnmefnll3PTTTelY8eO83TNOnXq5Jprrknv3r2zzjrrZNCgQWnbtm1Gjx6dkSNHpqqqKvfcc8+3XqNVq1bZfvvt86c//SktWrRInz59FsbtAgAs06ycBwAAlnjLL7987r333qy00ko56aSTcv7552fbbbfNeeedN9dz+vXrl4kTJ6Zz587ZcMMNaxzfa6+98vDDD6dt27b57W9/m8MPPzy33HJLunXrlkGDBi2ye/n5z3+e5s2b55xzzkmSnHDCCTnqqKPy4IMP5vDDD8/zzz+f4cOHp127dvN8zV69euXJJ5/MxhtvnN///vc59NBDM2zYsLRp0ya//vWv5+kaAwYMSPL1lkD2kwcA+P4qirktJQGWGhMmTEjz5s3T7ojbUqeycW2XAwAsRUadU54V1LPmM+PHj09VVVVZXpPq/vKXv2SXXXbJ448/nh49eszXueajAMCisiTPR62cBwAA4DtdffXV6dixY7p3717bpQAALBXsOQ8AALCQjB8/Pl9++eW39mnTpk2Zqlk4brnllrz00ksZPnx4Lr744lRUVNR2SQAASwXhPAAAwEJy+OGH5/rrr//WPkvazqJ77rlnmjZtmv333z+HHHJIbZcDALDUEM4DAAAsJL/5zW/Sv3//2i5joVrS/jEBAGBJIZwHAABYSNZee+2svfbatV0GAABLAB8ICwAAAAAAZSacBwAAAACAMhPOAwAAAABAmdlzHpYhr5y2Xaqqqmq7DAAAAABY5lk5DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMqsXm0XAAAAwLLhldO2S1VVVW2XAQCwWLByHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAos3q1XQCw6BVFkSSZMGFCLVcCALBgZs1jZs1rWLKYjwIAS7pFMR8VzsMyYMyYMUmSdu3a1XIlAADfz8SJE9O8efPaLoP5ZD4KACwtFuZ8VDgPy4CWLVsmSd5//32/zC5kEyZMSLt27fLBBx+kqqqqtstZqhjbRcfYLjrGdtExtovOkjK2RVFk4sSJWXnllWu7FBaA+ejia0l5D1gW+d4svnxvFl++N4uvpeF7syjmo8J5WAbUqfP1x0s0b958iX0DXNxVVVUZ20XE2C46xnbRMbaLjrFddJaEsRXqLrnMRxd/S8J7wLLK92bx5Xuz+PK9WXwt6d+bhT0f9YGwAAAAAABQZsJ5AAAAAAAoM+E8LAMqKyszePDgVFZW1nYpSx1ju+gY20XH2C46xnbRMbaLjrGlHPycLb58bxZfvjeLL9+bxZfvzeLL92bOKoqiKGq7CAAAAAAAWJZYOQ8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ52EpNnXq1Bx77LFZeeWV06hRo2y66aYZMWJEbZe12HrmmWfyq1/9Kuuss06aNGmSVVddNbvvvnveeuutGn1ff/31bL/99mnatGlatmyZffbZJ//+979r9Js5c2bOO++8rLbaamnYsGHWW2+9/PGPfyzH7SzWzjzzzFRUVKRr1641jv3f//1funfvnsaNG6dNmzY57LDDMmnSpBr9/HxX9/zzz2ennXZKy5Yt07hx43Tt2jWXXHJJtT7Gdv69/fbb2WOPPbLKKqukcePGWXPNNXP66adn8uTJ1foZ27mbNGlSBg8enO233z4tW7ZMRUVFhg0bNse+i+K9dV6vuSSal7GdOXNmhg0blp122int2rVLkyZN0rVr15xxxhmZMmXKHK977bXXZq211krDhg2z+uqr59JLL51jv9GjR2f33XdPixYtUlVVlZ133jnvvPPOwr5NlnDL4vtebTKfXXKYDy9+zKcXP+biiwfz+UWsAJZae+yxR1GvXr3i6KOPLq666qrihz/8YVGvXr3iiSeeqO3SFks/+9nPijZt2hSHHnpocfXVVxdDhgwpVlxxxaJJkybFyy+/XOr3wQcfFCussELRqVOn4uKLLy7OPPPMYrnllivWX3/9YurUqdWuedxxxxVJigMPPLAYOnRo0adPnyJJ8cc//rHct7fY+OCDD4rGjRsXTZo0KdZZZ51qx1544YWiYcOGxQYbbFBcccUVxYknnlhUVlYW22+/fY3r+Pn+rwcffLBo0KBBsemmmxYXXHBBMXTo0OLYY48tjjnmmFIfYzv/3n///aJFixZF+/bti7PPPru46qqrin333bdIUuy0006lfsb227377rtFkmLVVVctevXqVSQprrvuuhr9FsV76/xcc0k0L2M7ceLEIkmx2WabFWeccUYxdOjQYtCgQUWdOnWKXr16FTNnzqzW/8orryySFD/72c+KoUOHFvvss0+RpDjnnHNqXHf11VcvWrduXZx77rnFBRdcULRr165YZZVVis8//3xR3zpLkGXxfa82mc8uGcyHFz/m04sfc/HFh/n8oiWch6XUU089VSQpfvvb35bavvzyy6JTp07FD3/4w1qsbPH1t7/9rcab+1tvvVVUVlYWe++9d6nt4IMPLho1alS89957pbYRI0YUSYqrrrqq1Pbhhx8W9evXL375y1+W2mbOnFn06NGjWGWVVYqvvvpqEd7N4qtfv37F1ltvXfTs2bPGLyO9e/cuVlpppWL8+PGltquvvrpIUjz44IOlNj/f/zV+/PhixRVXLH76058WM2bMmGs/Yzv/zjzzzCJJ8corr1RrHzBgQJGkGDt2bFEUxva7TJkypfj444+LoiiKZ555Zq6T+UXx3jqv11xSzcvYTp06tfjb3/5W49zTTjutSFKMGDGi1DZ58uRi+eWXL/r06VOt79577100adKk9DNfFEVx7rnnFkmKp59+utT2+uuvF3Xr1i2OP/74hXF7LAWW1fe92mQ+u2QwH168mE8vnszFFx/m84uWcB6WUsccc0xRt27dav+DKoqiOOuss4okxfvvv19LlS15Ntxww2LDDTcsPW/dunWx22671ei3xhprFD/60Y9Kzy+77LIiSfHqq69W63fzzTcXSZbJf51/7LHHirp16xYvvfRSjV9Gxo8fX9SrV6/a6pSi+DpYatq0abH//vuX2vx8/9cVV1xRJClee+21oiiKYtKkSTV+qTC2C+bYY48tkhT//ve/a7TXqVOnmDRpkrGdT982mV8U763zes2lwbeN7Zy89NJLRZLikksuKbUNHz68SFIMHz68Wt//+7//K5IUN9xwQ6ntBz/4QfGDH/ygxnV//OMfF506dVqwm2Cp431v8WE+u/gwH178mE8vnszFF0/m8wufPedhKfXCCy9kjTXWSFVVVbX2TTbZJEnyj3/8oxaqWvIURZFPP/00K6ywQpKv99f97LPPsvHGG9fou8kmm+SFF14oPX/hhRfSpEmTrLXWWjX6zTq+LJkxY0YOPfTQHHDAAVl33XVrHH/55Zfz1Vdf1RjbBg0apFu3bjXG1s/31/73f/83VVVVGT16dLp06ZKmTZumqqoqBx98cGk/aWO7YHr16pUk2X///fOPf/wjH3zwQW699dZcccUVOeyww9KkSRNju5AsivfW+bnmsuiTTz5JktL/35L/jt3sY7bRRhulTp06peMzZ87MSy+9NNex/de//pWJEycuqtJZgnjfWzyYzy4+zIcXT+bTiydz8SWL+fyCE87DUurjjz/OSiutVKN9VttHH31U7pKWSDfddFNGjx6dfv36Jfl6XJPMdWzHjh2bqVOnlvquuOKKqaioqNEvWfa+B1deeWXee++9DBkyZI7Hv2tsvzlefr7/6+23385XX32VnXfeOdttt13uuOOO7LfffrnyyiszaNCgJMZ2QW2//fYZMmRIRowYkQ022CCrrrpq9thjjxx66KG58MILkxjbhWVRvLfOzzWXReedd16qqqrSu3fvUtvHH3+cunXrpnXr1tX6NmjQIMsvv3xpbGeNnZ9nvov3vcWD+eziw3x48WQ+vXgyF1+ymM8vuHq1XQCwaHz55ZeprKys0d6wYcPScb7dG2+8kV/+8pf54Q9/mIEDByb577h919hWVlb6HnzDmDFjcsopp+Tkk09Oq1at5tjnu8b2m+NlbP9r0qRJmTx5cg466KBccsklSZJdd90106ZNy1VXXZXTTz/d2H4PHTp0yJZbbpmf/exnWX755TN8+PCcddZZadOmTX71q18Z24VkUby3zs81lzVnnXVW/vd//zeXX355WrRoUWr/8ssv06BBgzme882f53kdW/C+V/vMZxcf5sOLL/PpxZe5+JLDfH7BCedhKdWoUaM5/gvirD/La9SoUblLWqJ88skn6dOnT5o3b57bb789devWTfLfcZuXsfU9+K+TTjopLVu2zKGHHjrXPt81tt8cL2P7X7Pudc8996zWvtdee+Wqq67Kk08+mcaNGycxtvPrlltuyc9//vO89dZbWWWVVZJ8/YvazJkzc+yxx2bPPff0c7uQLIr31vm55rLk1ltvzUknnZT9998/Bx98cLVjjRo1yrRp0+Z43jd/no0t88r7Xu0yn128mA8vvsynF0/m4ksW8/kFZ1sbWEqttNJKpT8B+qZZbSuvvHK5S1pijB8/Pr179864cePywAMPVBurWX9ONbexbdmyZelfbVdaaaV88sknKYqiRr9k2fkevP322xk6dGgOO+ywfPTRRxk1alRGjRqVKVOmZPr06Rk1alTGjh37nWM7+/fBz/fXZt3riiuuWK191rYU//nPf4ztArr88suzwQYblH4ZmGWnnXbK5MmT88ILLxjbhWRRvLfOzzWXFSNGjMiAAQPSp0+fXHnllTWOr7TSSpkxY0Y+++yzau3Tpk3LmDFjSmM7a+z8PPNdvO/VHvPZxYv58OLNfHrxZC6+ZDGfX3DCeVhKdevWLW+99VYmTJhQrf2pp54qHaemKVOm5Cc/+Uneeuut3HvvvVl77bWrHW/btm1atWqVZ599tsa5Tz/9dLVx7datWyZPnpzXX3+9Wr9l7XswevTozJw5M4cddlhWW2210uOpp57KW2+9ldVWWy2nn356unbtmnr16tUY22nTpuUf//hHjbH18/21jTbaKMnX4/xNs/bpa9WqlbFdQJ9++mlmzJhRo3369OlJkq+++srYLiSL4r11fq65LHjqqafy05/+NBtvvHFuu+221KtX8w9oZ43J7GP27LPPZubMmaXjderUybrrrjvHsX3qqafSsWPHNGvWbKHfA0se73u1w3x28WM+vHgzn148mYsvWcznv4cCWCr9/e9/L5IUv/3tb0ttU6ZMKTp37lxsuummtVjZ4uurr74qdtppp6JevXrF8OHD59rvoIMOKho1alS8//77pbb//d//LZIUV1xxRantgw8+KOrXr1/88pe/LLXNnDmz6NGjR9G2bdviq6++WjQ3spj597//Xdx11101Huuss06x6qqrFnfddVfx0ksvFUVRFNtvv32x0korFRMmTCidf8011xRJivvvv7/U5uf7v55//vkiSbHXXntVa99zzz2LevXqFaNHjy6KwtguiB133LFo0KBB8eabb1Zr32WXXYo6deoY2wXwzDPPFEmK6667rsaxRfHeOq/XXBp829i+9tprxfLLL1+ss846xdixY+d6jcmTJxctW7Ysdtxxx2rt/fv3Lxo3blyMGTOm1HbOOecUSYpnnnmm1PbGG28UdevWLY499tjvf0MsFbzvlZ/57OLJfHjxZj69eDIXXzyZzy98wnlYiu22225FvXr1imOOOaa46qqris0337yoV69e8dhjj9V2aYulww8/vEhS/OQnPyluuOGGGo9Z3n///WL55ZcvOnXqVFxyySXFWWedVSy33HLFuuuuW0yZMqXaNY855pgiSfHzn/+8uPrqq4s+ffoUSYqbbrqp3Le32OnZs2exzjrrVGt77rnnisrKymKDDTYorrjiiuLEE08sGjZsWPz4xz+ucb6f7//ab7/9iiTF7rvvXlx22WXFbrvtViQpjj/++FIfYzv/HnvssaJu3bpF69ati9NPP7247LLLit69exdJigMOOKDUz9h+t0svvbQYMmRIcfDBBxdJil133bUYMmRIMWTIkGLcuHFFUSya99b5ueaS6rvGdsKECUW7du2KOnXqFOecc06N/7f93//9X7XrXXbZZUWSom/fvsXVV19dDBgwoEhSnHnmmdX6TZgwoejUqVPRunXr4rzzzisuvPDCol27dsXKK69cfPbZZ+UcAhZzy+r7Xm0xn12ymA8vPsynFz/m4osX8/lFRzgPS7Evv/yyOProo4s2bdoUlZWVxQ9+8IPigQceqO2yFls9e/Ysksz18U2vvPJK8eMf/7ho3Lhx0aJFi2LvvfcuPvnkkxrXnDFjRnHWWWcV7du3Lxo0aFCss846xY033liuW1qszemXkaIoiieeeKLYfPPNi4YNGxatWrUqfvnLX1ZbBTGLn+//mjZtWnHqqacW7du3L+rXr1907ty5uPDCC2v0M7bz76mnnip69+5dtGnTpqhfv36xxhprFGeeeWYxffr0av2M7bdr3779XN9b33333VK/RfHeOq/XXFJ919i+++673/r/toEDB9a45tChQ4suXboUDRo0KDp16lRceOGFxcyZM2v0++CDD4q+ffsWVVVVRdOmTYsdd9yxePvtt8tw1yxJltX3vdpiPrtkMR9efJhPL57MxRcf5vOLTkVRzLb7PgAAAAAAsEj5QFgAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQAAAAAAKDPhPAAAAAAAlJlwHgAAAAAAykw4DwAAAAAAZSacBwAAAACAMhPOAwAAAABAmQnnAQAAAACgzITzAAAAAABQZsJ5AAAAAAAoM+E8AAAAAACUmXAeAAAAAADKTDgPAAAAAABlJpwHAAAAAIAyE84DAAAAAECZCecBAAAAAKDMhPMAAAAAAFBmwnkAAAAAACgz4TwAAAAAAJSZcB4AAAAAAMpMOA8AAAAAAGUmnAcAAAAAgDITzgMAAAAAQJkJ5wEAAAAAoMyE8wAAAAAAUGbCeQBYTAwbNiwVFRWpqKjIqaeeWtvlAADA9zZrftuhQ4faLmW+7LvvvqXaH3300douB1hK1avtAgCApcOwYcMyatSoJMkRRxyRFi1a1Go982vUqFEZNmxYkqRbt27ZZZddarUeAAAWHXM/YHEgnAcAFophw4blscceS/L1SqMlMZw/7bTTkiQDBw70CxoAwFLsu+Z+J554Yg444IAkybrrrlvu8oBlhHAeAPheJk+enMaNG9d2GQAAsNCsvvrqWX311Wu7DGApZ895AKgFjzzySH7wgx+kYcOG6dSpUy677LK59n333Xdz4IEHpn379qmsrEzr1q3Tr1+/vP7669X6zb5n/Y033ph11lknDRs2zNprr52bb765Wv9XXnkle++9d9Zee+20bNky9evXT+vWrdOnT588/vjj33rtK6+8Ml26dEn9+vVz2223paKiorRqPklWW221Uv9Ro0Zl1KhRpee9evXKyJEjs9FGG6VRo0bZcMMNS/t4XnHFFenYsWMaNmyYLbbYIi+++OJCHY+uXbumsrIya6yxRm677bZS3169emWrrbYqPb/++utL5+67775z/d4AACzt/v3vf+fII4/M6quvnsrKyiy33HLp06dP/v73v1fr9/nnn2fAgAFp3rx5WrRokQEDBuTzzz+f4zVPPfXU0lxr1tYySfLoo4/OdQ42duzYHH/88Vl77bXTuHHjVFVVZcMNN8zvf//7Up8///nP2WmnnbLaaqulWbNmadCgQdq3b59BgwaVtl9M5m3u9217zj/yyCPp06dPVlhhhTRo0CDt2rXLvvvum7fffnuu93ndddfloosuSufOnVNZWZn1118/jzzyyHeMPrDUKwCAsvrb3/5WNGjQoEhS7bHeeuuVvh48eHBRFEXx3HPPFS1atKjRN0nRtGnT4qmnnipd97rrrisd69KlyxzPufnmm0v9//jHP86xT5KiTp06xSOPPDLHa3fs2LFa328em9Pj3XffLd59993S87Zt2xYNGzas1qdRo0bF0UcfXePcDh06FNOnTy/VsaDjMXvNs+7xjTfeKIqiKHr27DnX+gcOHLiIfhIAABZv7733XrHKKqvMcY5Uv3794i9/+UtRFEUxderUYoMNNvjW+W379u1L1x08eHC1ueQsI0eOnOMc7P333y9WXXXVOdbRs2fPUr9f/OIXc53TrbjiisWnn35aFMW8zf0GDhxYahs5cmTpNS677LKioqJijuc2a9asePrpp+d4n3OajzZr1qwYO3bsQvt+AUseK+cBoMyOOuqoTJs2LUmyzTbb5J577smQIUPy6quvVutXFEUGDhyYcePGlc576KGHcu6556Zu3bqZNGlSBg0alKIoarzGm2++mcMPPzzDhw9P//79S+1HHnlkpk+fniTp0qVLfve73+XPf/5zHnnkkTz88MO54oorUllZmZkzZ+bss8+eY/3vvPNOtttuu/z5z3/ObbfdltVWWy1PPPFEunXrVurzpz/9KU888USeeOKJrLTSStXOHz16dLbZZpsMHz48W2+9dZLkyy+/zPnnn58DDjgg9957b9Zcc80kX+8F+uCDD37v8XjnnXey//775957782PfvSjJMnMmTNzzTXXJEkuvfTSXHLJJaX+vXv3LtV/4oknznEcAACWdoccckg+/PDDJMmAAQPywAMP5IorrkjTpk0zffr07Lfffvniiy9y3XXX5YUXXkiSLL/88vmf//mf/OlPf8qkSZMWWh3vv/9+kmTVVVfN0KFD88ADD+S8885Lu3btSv1+/OMf56qrrso999yTRx99NA888ECOOuqoJMmnn376ved+H3zwQX7961+nKIrUqVMnJ510UoYPH57ddtstSTJx4sTsu+++c52PHnvssbn77ruz/vrrl/rP/tetwLLFnvMAUEafffZZ6U+AKysrc+utt6Zly5bZcccd88Ybb+Smm24q9X3xxRfzyiuvJEm6detW+pCqzTffPJtsskmefPLJvPbaa3n++eez0UYbVXudLbbYIhdddFGSZLvttsvjjz+e999/P5988kn+/ve/p0ePHllvvfXy+OOP58wzz8wbb7yRSZMmVftF4tlnn53jPbRv3z733ntv6tWrPo1o3rx56euNN944HTp0mOP5jRo1yk033ZSqqqpMnjy59Oe8s37RqqioyOuvv55jjjkmSfLPf/7ze4/H+uuvX/plbIUVVsjDDz9c7drrrrtuxowZU+rfunXrdO/efY71AwAsC8aOHZv77rsvSdKmTZsceOCBSZKuXbtm2223zV133ZUxY8bkgQceyF/+8pfSeaeffnoGDRqUJGnRokW23XbbhVZH3bp188ADD2SttdZK8vU895t69eqVM888MxdccEHef//9fPnll9WOz5rfLujc7/bbby8tsvnpT3+aIUOGJEm23XbbPPHEE/nkk0/y2muv5cUXX6y2cCVJdt5555xzzjlJvv7Mpj322CPJf+ejwLJJOA8AZfTOO++Uvu7UqVNatmxZer7JJptUC+ffeuut0tf/+Mc/0qNHjzle8/XXX68RRm+66aalr+vWrZuNNtqotNronXfeSY8ePXLkkUdWWzE0u1kr1Ge3/fbb1wjm50eXLl1SVVWVJNXuf6ONNkpFRUWSrwP02ev4PuPRs2fP0tfLL798jWsDAFDdP//5z9LCjU8++eRb517fnOP+4Ac/KH29ySabLJQ6Zs6cmSTp2LFjKZif3YwZM7LNNtuUVvDPyfed+31zPvrN+Xb9+vWzwQYb5P777y/1mz2cNx8F5sS2NgCwmJgVTM+vL774Yr6vPW3atAwdOjRJUq9evZxzzjkZOXJknnjiiVIwPqc/x02SFVdccYHqnOWbK+zr1PnvVGRWYD+7udUxN3Maj+WWW6709Tf/YWF+rw0AQHXfNhed2/z2m+0zZswofT23D5CdF3/7299KwfxKK62U66+/Po8//nj++Mc/lvrMCvkXhe+ay5uPAnNi5TwAlNFqq61W+vqdd97Jf/7zn9JE/amnnqrWd4011ih93bNnzzz66KM1rjd58uQ0bty4RvvTTz9d+nrGjBnVtqjp2LFjxowZkylTpiT5esuXY489Nkny0UcfZezYsd96D3P7xeObQfui+MXn+4zHvFjU9QMALEk6d+6cioqKFEWRTp065c0330zdunWr9Zn1WUYvvvhi3nzzzSRfbx0za/X87PPbWb65WOOTTz4pff3AAw/MsY46depk5syZeeedd/LGG2+UPp/om0aPHl36eq+99sqAAQOSJLfccssca1iQud8356PfnG9Pnz692or9b/YD+DbCeQAooxVXXDGbbrppnnrqqUyZMiV77LFHDjvssLz44os1fnFYf/3107Vr17zyyit57LHHMmDAgOy2226pX79+Ro0alaeffjp33XVX/vOf/9R4nb/+9a858sgjs+222+aWW24pbWmz4oorZrPNNkvdunXTsGHDTJkyJS+//HKGDh2aFVdcMUOGDFngYPqbq4Guvvrq7LDDDmnUqFE23njjBbre7L7PeMxv/X/9619z//33p1mzZlljjTXSunXrhXIPAABLipYtW6Z3796577778q9//Ss77bRT9t9//zRr1izvvfdeXnjhhdx555158skns9NOO5W2dDnllFPSqFGjNG3aNMcff/wcr925c+fS1xdccEGaNm2af/7zn/mf//mfudYxfPjwzJgxI717985JJ52Udu3a5dVXX83zzz+fG264Ie3bty+dc8cdd6R79+75z3/+k+OOO26ONSzI3K9v37459thjM3369Nx5550ZPHhwNttss1x//fX5+OOPkyRrr7126QNfAb5TAQCU1eOPP17Ur1+/SFLtsfrqq5e+Hjx4cFEURfHcc88VLVq0qNH3m49ZrrvuulLbuuuuO8e+N9xwQ6n/L3/5yznW0Lp162+99qzaZnfppZfWuF779u2LoiiKd999t9TWs2fP0jkjR44stQ8cOPA7X29Bx+Ob15hbLdOnTy/atGlT43rXXXfdd35PAQCWRu+9916xyiqrfOvc69133y2mTp1arL/++t86v501LyyKopg2bVqx6qqr1ui/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dNBBufzyy3PGGWeU+iXJJ598kiuvvDK/+MUvvrWe5ZZbLqNGjaq23c2BBx6YNddcM5deemmuvfbaOZ43derUTJ06tfR8woQJ83T/AADLEtvaAAAALKBtttkmrVq1Srt27bLHHnukadOmueuuu9K2bdtSn4MPPnier7fbbruVgvkk2XTTTZMk/fv3LwXzs9qnTZuW0aNHl9q+GcxPnDgxn3/+eXr06JHJkyfnjTfeqPY6lZWVGTRo0HfWU7du3VIwP3PmzIwdOzZfffVVNt544zz//PNzPe/ss89O8+bNS4927dp952sBACxrrJwHAABYQJdddlnWWGON1KtXLyuuuGK6dOmSOnX+uwaqXr16WWWVVeb5equuumq157OC+tnD7Vnt//nPf0ptr776ak466aQ88sgjNVaqjx8/vtrztm3bzvOHv15//fX53e9+lzfeeCPTp08vta+22mpzPef444/PkUceWXo+YcIEAT0AwGyE8wAAAAtok002ycYbbzzX45WVldXC+u9St27d+WoviiJJMm7cuPTs2TNVVVU5/fTT06lTpzRs2DDPP/98jj322MycObPaed9cZf9tbrzxxuy7777ZZZddcswxx6R169apW7duzj777NL++nNSWVlZbRsdAABqEs4DAAAs4R599NGMGTMmd955Z7bccstS+7vvvvu9rnv77benY8eOufPOO1NRUVFqHzx48Pe6LgAA9pwHAABY4s1aWT9rJX2STJs2LZdffvlCv+5TTz2VJ5988ntdFwAAK+cBAACWeJtvvnmWW265DBw4MIcddlgqKipyww03VAvVF8SOO+6YO++8Mz/96U/Tp0+fvPvuu7nyyiuz9tprZ9KkSQupegCAZZOV8wAAAEu45ZdfPvfee29WWmmlnHTSSTn//POz7bbb5rzzzvte1913331z1lln5cUXX8xhhx2WBx98MDfeeOO37rMPAMC8qSi+71IKYLE3YcKENG/ePO2OuC11KhvXdjkZdU6f2i4BAFjCzJrPjB8/PlVVVbVdDvNpcZuPfl/mswCw7FkU81Er5wEAAAAAoMyE8wAAAAAAUGbC+TIbNmxYKioq8uyzz87xeK9evdK1a9cyV1Vejz76aCoqKkqPunXrpnXr1unbt29ef/312i4PAAAAAGCRq1fbBbDsOuyww/KDH/wg06dPz0svvZQrr7wyjz76aF555ZW0adOmtssDAAAAAFhkhPPUmh49eqRv376l5126dMnBBx+cP/zhD/nNb35Ti5UtuKIoMmXKlDRq1Ki2SwEAAAAAFmO2tVnMjRo1KhUVFRk2bFiNYxUVFTn11FNLz0899dRUVFTkrbfeSv/+/dO8efO0atUqJ598coqiyAcffJCdd945VVVVadOmTX73u99Vu960adNyyimnZKONNkrz5s3TpEmT9OjRIyNHjpxjTeeff36GDh2aTp06pbKyMj/4wQ/yzDPPLPC99ujRI0nyr3/9q1r76NGjs99++2XFFVdMZWVl1llnnfzP//xPjfMvvfTSrLPOOmncuHGWW265bLzxxrn55pur9XnhhRfSu3fvVFVVpWnTpvnRj36Uv//979X6zBrH2c3akmjUqFGltg4dOmTHHXfMgw8+mI033jiNGjXKVVddlSQZN25cfv3rX6dDhw6prKzMKquskgEDBuTzzz8vnT916tQMHjw4nTt3TmVlZdq1a5ff/OY3mTp1arXXHjFiRLp3754WLVqkadOm6dKlS0444YR5GFUAAAAAYHFk5XwtGT9+fLWQdpbp06d/72v369cva621Vs4555wMHz48Z5xxRlq2bJmrrroqW2+9dc4999zcdNNNOfroo/ODH/wgW265ZZJkwoQJueaaa7LnnnvmwAMPzMSJE3Pttddmu+22y9P/j737Do+qeP8+/tn0XoCEGkLoXTrSq7RApElTkSBdKV8FAUEgdAtFQJpIUUAJHUWaGoqIWOiIUiR0pSfUAMl5/siT/bFuAiSEXUjer+va68rOmZ1zn5ldmNyZnfPLLypTpozFeRYvXqxr166pe/fuMplM+uCDD9SyZUv9/fffcnZ2TnXcSUlvf39/c9m///6r559/XiaTSW+++aYCAgK0bt06vf7664qNjVW/fv0kSZ9++qn69Omj1q1bq2/fvrp9+7b27dunnTt3qkOHDpKkgwcPqkaNGvLx8dE777wjZ2dnzZo1S7Vr19aWLVtUuXLl1He2pL/++kvt27dX9+7d1bVrVxUpUkTXr19XjRo1dOjQIXXu3FnlypXTxYsXtWbNGp0+fVrZsmVTQkKCwsLC9OOPP6pbt24qVqyY9u/fr0mTJunw4cNatWqVOe6mTZuqdOnSGjlypFxdXXX06FFt3749TfECAAAAAAAAsD+S83ZSv379FI+VKFHisdquVKmSefV2t27dlC9fPr399tsaN26cBg4cKElq3769cuXKpblz55qT8/7+/oqOjpaLi4u5ra5du6po0aKaOnWqPvvsM4vznDx5UkeOHDEn04sUKaIXX3xRGzZsUNOmTR8a57Vr13Tx4kXznvP9+vWTyWRSq1atzHWGDBmi+Ph47d+/X1mzZpUk9ejRQ+3bt9eIESPUvXt3ubu7a+3atSpRooSWLl2a4vmGDh2qu3fv6scff1T+/PklSR07dlSRIkX0zjvvaMuWLQ+NOTlHjx7V+vXr1bBhQ3PZ8OHDdeDAAa1YsUItWrSwiMEwDEmJf9z47rvvtGXLFlWvXt1cp2TJkurRo4d++uknVa1aVZs2bdKdO3e0bt06ZcuW7ZFiiouLs1h9Hxsbm6ZrAwAAAAAAAPBksK2NnXzyySfatGmT1aN06dKP3XaXLl3MPzs6OqpChQoyDEOvv/66udzPz09FihTR33//bVE3KTGfkJCgy5cv6969e6pQoYJ27dpldZ62bdtarHJP2pbm/jYfpHPnzgoICFCuXLnUqFEjxcTE6IsvvlDFihUlJe7fvnz5cjVr1kyGYejixYvmR8OGDRUTE2OOy8/PT6dPn05xW534+Hht3LhRzZs3NyfmJSlnzpzq0KGDfvzxxzQnsENCQiwS85K0fPlyPffccxaJ+SRJW+YsXbpUxYoVU9GiRS2urW7dupJk3k7Iz89PkrR69WolJCQ8Ukzjxo2Tr6+v+REUFJSmawMAAAAAAADwZJCct5NKlSqpfv36Vo/7k91plTdvXovnvr6+cnNzs1p17evrqytXrliULViwQKVLl5abm5uyZs2qgIAArV27VjExMQ89T1Ls/20zJcOGDdOmTZu0cuVKdezYUTExMXJw+L+35IULF3T16lXNnj1bAQEBFo/w8HBJ0vnz5yVJAwcOlJeXlypVqqRChQrpjTfesNj25cKFC7p586aKFCliFUexYsWUkJCgU6dOPVLc/xUSEmJVduzYMZUsWfKBrzty5IgOHjxodW2FCxe2uLa2bduqWrVq6tKli7Jnz6527dopMjLygYn6wYMHKyYmxvxI67UBAAAAAAAAeDLY1uYpl9yNSaXEleApcXR0fKQySeYtViRp4cKF6tSpk5o3b64BAwYoMDBQjo6OGjdunNVNWh+1zQcpVaqUeXuf5s2b6+bNm+ratauqV6+uoKAgc/L5lVde0WuvvZZsG0nfNChWrJj++usvffPNN1q/fr2WL1+u6dOna9iwYYqIiHikeJKkts/d3d1T1X6ShIQElSpVShMnTkz2eNJqd3d3d23dulVRUVFau3at1q9fryVLlqhu3brauHFjsuPg6uoqV1fXNMUFAAAAAAAA4MkjOf+US1qNfvXqVYvyEydOpPu5li1bpvz582vFihUWCerhw4en+7mSM378eK1cuVJjxozRzJkzFRAQIG9vb8XHxz9wj/4knp6eatu2rdq2bas7d+6oZcuWGjNmjAYPHqyAgAB5eHjor7/+snrdn3/+KQcHB3My/P4+T9pSRkpdnxcoUEAHDhx4aJ29e/eqXr16Kf5BIImDg4Pq1aunevXqaeLEiRo7dqyGDBmiqKioR+obAAAAAAAAAE8XtrV5yvn4+ChbtmzaunWrRfn06dPT/VxJK7DvX/m+c+dO7dixI93PlZwCBQqoVatWmj9/vv755x85OjqqVatWWr58ebKJ7gsXLph/vnTpksUxFxcXFS9eXIZh6O7du3J0dFSDBg20evVqRUdHm+v9+++/Wrx4sapXry4fHx9zHJIs+vzGjRtasGDBI19Lq1attHfvXq1cudLqWFL/tmnTRmfOnNGnn35qVefWrVu6ceOGJOny5ctWx8uUKSNJFjd9BQAAAAAAAPDsYOX8M6BLly4aP368unTpogoVKmjr1q06fPhwup+nadOmWrFihVq0aKHQ0FAdP35cM2fOVPHixXX9+vV0P19yBgwYoMjISE2ePFnjx4/X+PHjFRUVpcqVK6tr164qXry4Ll++rF27dum7774zJ64bNGigHDlyqFq1asqePbsOHTqkadOmKTQ0VN7e3pKk0aNHa9OmTapevbp69eolJycnzZo1S3Fxcfrggw/MMTRo0EB58+bV66+/rgEDBsjR0VFz585VQECATp48+cjXsWzZMr300kvq3Lmzypcvr8uXL2vNmjWaOXOmnnvuOb366quKjIxUjx49FBUVpWrVqik+Pl5//vmnIiMjtWHDBlWoUEEjR47U1q1bFRoaquDgYJ0/f17Tp09Xnjx5VL169fQfBAAAAAAAAABPHMn5Z8CwYcN04cIFLVu2TJGRkWrcuLHWrVunwMDAdD1Pp06d9M8//2jWrFnasGGDihcvroULF2rp0qXavHlzup4r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Wr9+vdq0aWPeIuZBVq5caU7MFy1aVEuWLLHaXuRx47QFf39/889OTv+3ljQp4Z5ekptjPsq5vb29FRYWJkn68ccfdfz4cX377beSpJo1a5q3jnwU//3DxMP896a7/5XavvP19TX/7ODwf6lBHx+fZOunZgzu3bunuLi4x44RyCxIzgMAkMEULFjQPMn++++/k129cubMGfPPHTp0UMeOHVNcXfRfyf1yULhwYfPPf//9twzDsHok7Ul/f93hw4cnW/fGjRvm/eofdm4AAIC0cHJyUrdu3bR69WodPXpUV65cUdWqVSVJGzdutNjb+1HmS/cnOR81GW4YhoKDgzV+/Hht27ZNFy9e1K+//mo+nrRX/IPcP69744031KZNG1WvXl23b9+2qnv/POyXX37RxYsXU2w3Ldfz3/aTHDhwQDdv3pSUmKRN7xX7UuIcOGmuWKBAAd27d89qjnnnzh2NHDkyzed4+eWXJSX2R/fu3c2J/ldeeSVV7TxsPr17927du3fP/Dzp3k3/rWdr95973rx5Kc7jk1bxp1Za3nPAs45tbQAAyGCyZMmixo0ba+3atYqPj1fjxo01dOhQBQUF6eDBg9q1a5d69uxprr98+XJVr15dV65c0aBBg9J0zpdffll79+6VJDVt2lTvvPOO8uTJo3PnzunPP//U6tWr9fbbb6tTp05q3bq1Bg0apLi4OI0fP14mk0lVqlTRzZs3dfz4cUVFRenWrVvatGlTuvQHAABAcgoUKKBWrVrpueeeU65cuXT+/HkdP35cUmLSPCQkxFz3UeZL968M/vHHH7Vu3Tp5e3urcOHCKa6U/vLLLzVz5kw1b95cISEh8vX11Q8//GA+ntwK5P8KDg42/zx37lzlz59fR48e1ejRo63qPvfccypZsqQOHDigmJgY1atXT++8846yZMmi33//XVeuXNGECROsrmf58uUKCQmRs7OzKlasmGLytUOHDlqzZo0kadiwYXJ1dVW2bNkUERFhrtO2bdsnsuAiaQ787bff6tixYwoLC9Prr78ub29vnThxQrt379aKFSu0Y8cO5cuXL03naNSokbJmzapLly6Z56qurq5q3br1Y8dfpkwZFStWTIcOHdK5c+f08ssvq1OnTtq5c6dWrlwpSXJxcVGrVq0e+1xp1aFDB3388ceSpP/973+6fPmySpcuratXr+rYsWPauHGjgoODNXfu3DS1f/97buHChXJ0dJSjo6OqV6+eLvEDTyOS8wAAZEDTp09XtWrVdPr0aUVHR6tLly7mY7Vq1VLlypVVunRp7du3T9HR0WrRooUkqVq1ajp//nyqz9e3b19t2LBB33//vf744w916tQpxbp58uTRtGnT1L17d8XFxWnEiBFWde7fkxIAAOBJOHnypD766KNkjzVs2DDV86VixYopR44c+ueff3T8+HE1adJEUuIK45TmRgkJCdq2bZu2bduW7PH27ds/9DqaNWumnDlz6ty5c9q9e7dCQ0PNcW7fvt2irslk0oIFC1SvXj1dvXpV+/bts1j1/dprr5l/rl27tkwmkwzD0LfffmvewuX48eMpJrfbtGmjlStXasmSJbp8+bK6du1qcbxo0aLJ7lOeXmbMmGGeA98fc3pxdnZWmzZtNGPGDHNZaGio/Pz8Hrttk8mk+fPnq379+rp27ZoiIyMVGRlpcXzy5Mmp2j4nvVWqVEnvvfeeRo0apatXr+rtt9+2qnP/eyi16tSpo4kTJ0qyvDcVW98gI2NbGwAAMqC8efNq9+7deuedd1S0aFG5ubnJy8tLZcqUUevWreXo6Ki1a9fqxRdflK+vrwICAtS3b1/NmTMnTedzcXHR+vXrNWXKFFWqVEne3t5yc3NTSEiIQkND9dlnn5l/oZWkLl26aOvWrWrZsqWyZ88uJycnZc+e3Tzhnz59enp1BQAAQLLGjh2rhg0bKk+ePHJ1dZWrq6uKFCmiAQMGaOnSpameLzk5OWnNmjWqXr26vL29HymGKlWqqG/fvipXrpyyZcsmR0dH+fr6qkaNGlqyZInatWv30Da8vb21adMm1a1bV15eXsqdO7dGjhyZ4vYt5cqV0969e9WzZ0/lz59fLi4u8vPz0/PPP6/GjRub65UqVUqff/65ihUr9sjblJhMJi1evFgzZ85UpUqV5OnpKVdXVxUuXFiDBg3Szz//bLE6Or0lzYEHDBhgngN7e3uraNGi6tixo9asWfPYye3/bmGT2i1tHqRSpUr6/fff9dprryl37txycnKSv7+/GjVqpI0bN1p8+9VeRo4cqW+++cb8LQJnZ2flzp1b1atX1/jx4y2+JZFaTZs21UcffaQCBQpY7EsPZGQmgz8/AQAAAAAAAABgU/wZCgAAAAAAAE+t8+fP6/Dhww+sw77kAJ5FJOcBAAAAAADw1Pr2228VHh7+wDpsDAHgWcSe8wAAAAAAAAAA2Bh7zgMAAAAAAAAAYGOsnAcAAAAAAAAAwMZIzgMAAAAAAAAAYGPcEBbIBBISEnT27Fl5e3vLZDLZOxwAAIBUMwxD165dU65cueTgwBqjZw3zUQAA8Kx7EvNRkvNAJnD27FkFBQXZOwwAAIDHdurUKeXJk8feYSCVmI8CAICMIj3noyTngUzA29tbUuI/Hj4+PnaOBgAAIPViY2MVFBRkntfg2cJ8FAAAPOuexHyU5DyQCSR9ddjHx4dfhgAAwDONLVGeTcxHAQBARpGe81E2awQAAAAAAAAAwMZIzgMAAAAAAAAAYGMk5wEAAAAAAAAAsDGS8wAAAP+PvTsPi6r8/z/+GhYHEEFUwA0FcSvX1FxSXNLcNS0zxV0z1ErJtEJzwV3LrU3Ncg0s1xbN/eNeWn3VzKVcErdP5srgigrn94c/5+M0qKAwI/B8XNdcl3Of+5zzOjfIdebNzX0AAAAAAHAwivMAAAAAAAAAADgYxXkAAAAAAAAAAByM4jwAAAAAAAAAAA5GcR4AAAAAAAAAAAejOA8AAAAAAAAAgINRnAcAAAAAAAAAwMEozgMAAAAAAAAA4GAU5wEAAAAAAAAAcDCK8wAAAAAAAAAAOJibswMAcJyyw1bLxeyVIceOG9csQ44LAAAAAAAAZEXMnAcAAAAAAAAAwMEozgMAAAAAAAAA4GAU5wEAAAAAAAAAcDCK8wAAAAAAAAAAOBjFeQAAAAAAAAAAHIziPAAAAAAAAAAADkZxHgAAAAAAAAAAB3NzdgAAAAAAQPZQdthquZi9nB0DADKduHHNnB0BQAZg5jwAAAAAAAAAAA5GcR4AAAAAAAAAAAejOO9gc+bMkclk0q+//pri9rp166ps2bIOTuVYGzdulMlksr5cXV0VEBCgNm3a6MCBA86OBwAAAAAAAAAZjjXn4TR9+/bV008/rZs3b2rPnj2aPn26Nm7cqL179yp//vzOjgcAAAAAAAAAGYbiPJwmLCxMbdq0sb4vVaqUevfurXnz5untt992YrKHZxiGrl+/Lk9PT2dHAQAAAAAAAPAYY1mbx1xcXJxMJpPmzJljt81kMmn48OHW98OHD5fJZNLBgwfVsWNH+fr6yt/fX0OGDJFhGDpx4oSef/55+fj4KH/+/Jo4caLN8W7cuKGhQ4eqcuXK8vX1Vc6cORUWFqYNGzakmOmDDz7QZ599ptDQUJnNZj399NP65ZdfHvpaw8LCJElHjhyxaT916pS6d++uwMBAmc1mlSlTRrNmzbLb/6OPPlKZMmXk5eUlPz8/ValSRbGxsTZ9du3apSZNmsjHx0fe3t6qX7++tm/fbtPnzjj+250lieLi4qxtwcHBat68uVavXq0qVarI09NTM2bMkCTFx8frzTffVHBwsMxmswoXLqzOnTvr3Llz1v0TExM1bNgwFS9eXGazWUFBQXr77beVmJhoc+61a9eqVq1ayp07t7y9vVWqVCkNGjQoFaMKAAAAAAAA4HHEzHknsVgsNkXaO27evPnIx3755Zf1xBNPaNy4cVqxYoVGjRqlPHnyaMaMGXr22Wc1fvx4xcTEaMCAAXr66adVu3ZtSVJCQoI+//xztW/fXj179tSlS5f0xRdfqFGjRvr5559VsWJFm/PExsbq0qVLioiIkMlk0oQJE/TCCy/or7/+kru7e5pz3yl6+/n5Wdv++ecfVa9eXSaTSa+//rr8/f21cuVK9ejRQwkJCYqMjJQkzZw5U3379lWbNm3Ur18/Xb9+XXv27NGOHTsUHh4uSdq3b5/CwsLk4+Ojt99+W+7u7poxY4bq1q2rTZs2qVq1amkfbEl//vmn2rdvr4iICPXs2VOlSpXS5cuXFRYWpgMHDqh79+6qVKmSzp07p++++04nT55Uvnz5lJycrJYtW2rr1q169dVX9cQTT+j333/X5MmTdfDgQX3zzTfW3M2bN1f58uU1YsQImc1mHT58WNu2bXuovAAAAAAAAACcj+K8kzRo0OCe28qUKfNIx65atap19varr76q4OBgvfXWWxo7dqzeeecdSVL79u1VsGBBzZo1y1qc9/PzU1xcnHLkyGE9Vs+ePVW6dGl99NFH+uKLL2zOc/z4cR06dMhaTC9VqpSef/55rV69Ws2bN39gzkuXLuncuXPWNecjIyNlMpn04osvWvsMHjxYSUlJ+v3335U3b15JUq9evdS+fXsNHz5cERER8vT01IoVK1SmTBktWrTonud77733dPPmTW3dulXFihWTJHXu3FmlSpXS22+/rU2bNj0wc0oOHz6sVatWqVGjRta2YcOGae/evVq6dKlat25tk8EwDEm3f7mxbt06bdq0SbVq1bL2KVu2rHr16qUff/xRzzzzjNauXasbN25o5cqVypcvX6oyJSYm2sy+T0hIeKhrAwAAAAAAAJAxWNbGST755BOtXbvW7lW+fPlHPvYrr7xi/berq6uqVKkiwzDUo0cPa3vu3LlVqlQp/fXXXzZ97xTmk5OTdeHCBd26dUtVqlTRzp077c7z8ssv28xyv7Mszd3HvJ/u3bvL399fBQsWVOPGjWWxWDR//nw9/fTTkm6v375kyRK1aNFChmHo3Llz1lejRo1ksVisuXLnzq2TJ0/ec1mdpKQkrVmzRq1atbIW5iWpQIECCg8P19atWx+6gB0SEmJTmJekJUuWqEKFCjaF+TvuLJmzaNEiPfHEEypdurTNtT377LOSZF1OKHfu3JKkb7/9VsnJyanKNHbsWPn6+lpfQUFBD3VtAAAAAAAAADIGxXknqVq1qho0aGD3urvY/bCKFCli897X11ceHh52s659fX118eJFm7a5c+eqfPny8vDwUN68eeXv768VK1bIYrE88Dx3sv/7mPcydOhQrV27VsuWLVPnzp1lsVjk4vK/b8mzZ88qPj5en332mfz9/W1e3bp1kySdOXNGkvTOO+/I29tbVatWVYkSJfTaa6/ZLPty9uxZXb16VaVKlbLL8cQTTyg5OVknTpxIVe5/CwkJsWs7cuSIypYte9/9Dh06pH379tldW8mSJW2u7eWXX1bNmjX1yiuvKDAwUO3atdPChQvvW6iPioqSxWKxvh722gAAAAAAAABkDJa1ecyl9GBS6fZM8HtxdXVNVZsk6xIrkvTll1+qa9euatWqlQYOHKiAgAC5urpq7Nixdg9pTe0x76dcuXLW5X1atWqlq1evqmfPnqpVq5aCgoKsxeeOHTuqS5cuKR7jzl8aPPHEE/rzzz+1fPlyrVq1SkuWLNGnn36qoUOHKjo6OlV57kjrmHt6eqbp+HckJyerXLlymjRpUorb78x29/T01ObNm7VhwwatWLFCq1at0tdff61nn31Wa9asSfHrYDabZTabHyoXAAAAAAAAgIxHcf4xd2c2enx8vE37sWPH0v1cixcvVrFixbR06VKbAvWwYcPS/VwpGTdunJYtW6bRo0dr+vTp8vf3V65cuZSUlHTfNfrvyJkzp15++WW9/PLLunHjhl544QWNHj1aUVFR8vf3l5eXl/7880+7/f744w+5uLhYi+F3j/mdJWWktI15aGio9u7d+8A+v/32m+rXr3/PXwjc4eLiovr166t+/fqaNGmSxowZo8GDB2vDhg2pGhsAAAAAAAAAjxeWtXnM+fj4KF++fNq8ebNN+6effpru57ozA/vume87duzQTz/9lO7nSkloaKhefPFFzZkzR6dPn5arq6tefPFFLVmyJMVC99mzZ63/Pn/+vM22HDly6Mknn5RhGLp586ZcXV3VsGFDffvtt4qLi7P2++effxQbG6tatWrJx8fHmkOSzZhfuXJFc+fOTfW1vPjii/rtt9+0bNkyu213xrdt27Y6deqUZs6cadfn2rVrunLliiTpwoULdtsrVqwoSTYPfQUAAAAAAACQeTBzPhN45ZVXNG7cOL3yyiuqUqWKNm/erIMHD6b7eZo3b66lS5eqdevWatasmY4eParp06frySef1OXLl9P9fCkZOHCgFi5cqClTpmjcuHEaN26cNmzYoGrVqqlnz5568skndeHCBe3cuVPr1q2zFq4bNmyo/Pnzq2bNmgoMDNSBAwf08ccfq1mzZsqVK5ckadSoUVq7dq1q1aqlPn36yM3NTTNmzFBiYqImTJhgzdCwYUMVKVJEPXr00MCBA+Xq6qpZs2bJ399fx48fT/V1LF68WC+99JK6d++uypUr68KFC/ruu+80ffp0VahQQZ06ddLChQvVq1cvbdiwQTVr1lRSUpL++OMPLVy4UKtXr1aVKlU0YsQIbd68Wc2aNVPRokV15swZffrppypcuLBq1aqV/l8EAAAAAAAAABmO4nwmMHToUJ09e1aLFy/WwoUL1aRJE61cuVIBAQHpep6uXbvq9OnTmjFjhlavXq0nn3xSX375pRYtWqSNGzem67nupUqVKqpbt66mTZumqKgoBQYG6ueff9aIESO0dOlSffrpp8qbN6/KlCmj8ePHW/eLiIhQTEyMJk2apMuXL6tw4cLq27ev3nvvPWufMmXKaMuWLYqKitLYsWOVnJysatWq6csvv1S1atWs/dzd3bVs2TL16dNHQ4YMUf78+RUZGSk/Pz/rg2gfxNvbW1u2bNGwYcO0bNkyzZ07VwEBAapfv74KFy4s6fZSNd98840mT56sefPmadmyZfLy8lKxYsXUr18/64NhW7Zsqbi4OM2aNUvnzp1Tvnz5VKdOHUVHR8vX1zc9hh0AAAAAAACAg5mM1D69E0CmlZCQIF9fXwVFLpSL2StDzhE3rlmGHBcAAED63/2MxWKxLkeIzMMR96MAkJXxmRtwvoy4H2XNeQAAAAAAAAAAHIziPAAAAAAAAAAADkZxHgAAAACygDlz5shkMunXX391dhQAAACkAsV5AAAAAAAAAAAcjOI8AAAAAAAAAAAORnEeAAAAALKJXbt2qUmTJvLx8ZG3t7fq16+v7du3W7fHx8fL1dVVH374obXt3LlzcnFxUd68eWUYhrW9d+/eyp8/v0PzAwAAZCUU5wEAAAAgG9i3b5/CwsL022+/6e2339aQIUN09OhR1a1bVzt27JAk5c6dW2XLltXmzZut+23dulUmk0kXLlzQ/v37re1btmxRWFiYw68DAAAgq6A4DwAAAADZwHvvvaebN29q69ateu+99/TOO+9o27ZtypEjh95++21rv7CwMG3dutX6fsuWLapVq5YCAgK0ZcsWSbIW6u9VnE9MTFRCQoLNCwAAALbcnB0AgOPsjW4kHx8fZ8cAAACAgyUlJWnNmjVq1aqVihUrZm0vUKCAwsPDNXPmTCUkJMjHx0dhYWH65JNP9Oeff6pUqVLasmWLGjVqJH9/f23ZskW9evXS1q1bZRjGPYvzY8eOVXR0tKMuDwAAIFNi5jwAAAAAZHFnz57V1atXVapUKbttTzzxhJKTk3XixAlJshbct2zZoitXrmjXrl0KCwtT7dq1rTPnt2zZIh8fH1WoUCHF80VFRclisVhfd44NAACA/2HmPAAAAADAqmDBggoJCdHmzZsVHBwswzBUo0YN+fv7q1+/fjp27Ji2bNmiZ555Ri4uKc/3MpvNMpvNDk4OAACQuTBzHgAAAACyOH9/f3l5eenPP/+02/bHH3/IxcVFQUFB1rawsDBt2bJFW7ZsUcWKFZUrVy5VqFBBvr6+WrVqlXbu3KnatWs78hIAAACyHIrzAAAAAJDFubq6qmHDhvr2228VFxdnbf/nn38UGxurWrVq2TybKCwsTHFxcfr666+ty9y4uLjomWee0aRJk3Tz5s17rjcPAACA1GFZGwAAAADIQmbNmqVVq1bZtQ8fPlxr165VrVq11KdPH7m5uWnGjBlKTEzUhAkTbPreKbz/+eefGjNmjLW9du3aWrlypcxms55++umMvRAAAIAsjuI8AAAAAGQh06ZNS7G9a9eu2rJli6KiojR27FglJyerWrVq+vLLL1WtWjWbvqVKlVJAQIDOnDmjWrVqWdvvFO2rVq3KmvIAAACPyGQYhuHsEAAyVkJCgnx9fWWxWGz+XBkAACCz4H4mc7vz9QuKXCgXs5ez4wBAphM3rpmzIwDZXkbcj7LmPAAAAAAAAAAADkZxHgAAAAAAAAAAB6M4DwAAAAAAAACAg1GcBwAAAAAAAADAwSjOAwAAAAAAAADgYBTnAQAAAAAAAABwMIrzAAAAAAAAAAA4GMV5AAAAAAAAAAAcjOI8AAAAAAAAAAAORnEeAAAAAAAAAAAHozgPAAAAAAAAAICDUZwHAAAAAAAAAMDBKM4DAAAAAAAAAOBgFOcBAAAAAAAAAHAwivMAAAAAAAAAADgYxXkAAAAAAAAAAByM4jwAAAAAAAAAAA7m5uwAAAAAAIDsYW90I/n4+Dg7BgAAwGOBmfMAAAAAAAAAADgYxXkAAAAAAAAAAByM4jwAAAAAAAAAAA5GcR4AAAAAAAAAAAejOA8AAAAAAAAAgINRnAcAAAAAAAAAwMEozgMAAAAAAAAA4GBuzg4AwHHKDlstF7OXs2M8tuLGNXN2BAAAAAAAAGQTzJwHAAAAAAAAAMDBKM4DAAAAAAAAAOBgFOcBAAAAAAAAAHAwivMAAAAAAAAAADgYxXkAAAAAAAAAAByM4jwAAAAAAAAAAA5GcR4AAAAAAAAAAAejOA8AAAAAAAAAgINRnAcyiMlk0uuvv+7sGAAAAAAAAAAeQxTngRTs27dPHTt2VKFChWQ2m1WwYEF16NBB+/bts+n3448/avjw4YqPj3dOUAAAAAAAAACZEsV54F+WLl2qSpUqaf369erWrZs+/fRT9ejRQxs2bFClSpW0bNkya98ff/xR0dHRFOcBAAAAAAAApImbswMAj5MjR46oU6dOKlasmDZv3ix/f3/rtn79+iksLEydOnXSnj17VKxYMScmve369evKkSOHXFz4PRsAAAAAAACQmVDRA+7y/vvv6+rVq/rss89sCvOSlC9fPs2YMUNXrlzRhAkTNHz4cA0cOFCSFBISIpPJJJPJpLi4OJv9vvnmG5UtW1Zms1llypTRqlWr7M576tQpde/eXYGBgdZ+s2bNsumzceNGmUwmffXVV3rvvfdUqFAheXl5KSEhIX0HAQAAAAAAAECGY+Y8cJfvv/9ewcHBCgsLS3F77dq1FRwcrBUrVmjFihU6ePCgFixYoMmTJytfvnySZFPU37p1q5YuXao+ffooV65c+vDDD/Xiiy/q+PHjyps3ryTpn3/+UfXq1a0PkPX399fKlSvVo0cPJSQkKDIy0ibDyJEjlSNHDg0YMECJiYnKkSNHxgwGAAAAAAAAgAxDcR74/ywWi/773//q+eefv2+/8uXL67vvvlNISIgqVaqkBQsWqFWrVgoODrbre+DAAe3fv1+hoaGSpHr16qlChQpasGCBXn/9dUnS4MGDlZSUpN9//91asO/Vq5fat2+v4cOHKyIiQp6entZjXr9+Xb/++qtN278lJiYqMTHR+p7Z9QAAAAAAAMDjhWVtgP/v0qVLkqRcuXLdt9+d7akpeDdo0MBamJduF/Z9fHz0119/SZIMw9CSJUvUokULGYahc+fOWV+NGjWSxWLRzp07bY7ZpUuX+xbmJWns2LHy9fW1voKCgh6YFQAAAAAAAIDjUJwH/r87Rfc7Rfp7SW0RX5KKFCli1+bn56eLFy9Kks6ePav4+HjrGvd3v7p16yZJOnPmjM3+ISEhDzxvVFSULBaL9XXixIkH7gMAAAAAAADAcVjWBvj/fH19VaBAAe3Zs+e+/fbs2aNChQrJx8fngcd0dXVNsd0wDElScnKyJKljx47q0qVLin3Lly9v8/5Bs+YlyWw2y2w2P7AfAAAAAAAAAOegOA/cpXnz5po5c6a2bt2qWrVq2W3fsmWL4uLiFBERIUkymUyPdD5/f3/lypVLSUlJatCgwSMdCwAAAAAAAEDmwbI2wF0GDhwoT09PRURE6Pz58zbbLly4oF69esnLy0sDBw6UJOXMmVOSFB8f/1Dnc3V11YsvvqglS5Zo7969dtvPnj37UMcFAAAAAAAA8Hhj5jxwlxIlSmju3Lnq0KGDypUrpx49eigkJERxcXH64osvdO7cOS1YsMD6kNfKlStLkgYPHqx27drJ3d1dLVq0sBbtU2PcuHHasGGDqlWrpp49e+rJJ5/UhQsXtHPnTq1bt04XLlzIkGsFAAAAAAAA4DwU54F/eemll1S6dGmNHTvWWpDPmzev6tWrp0GDBqls2bLWvk8//bRGjhyp6dOna9WqVUpOTtbRo0fTVJwPDAzUzz//rBEjRmjp0qX69NNPlTdvXpUpU0bjx4/PiEsEAAAAAAAA4GQm486TKQFkWQkJCfL19VVQ5EK5mL2cHeexFTeumbMjAACAe7hzP2OxWOTj4+PsOEgjvn4AACCzy4j7GdacBwAAAAAAAADAwSjOAwAAAAAAAADgYBTnAQAAAAAAAABwMIrzAAAAAAAAAAA4GMV5AAAAAAAAAAAcjOI8AAAAgEzl+PHjMgzDrt0wDB0/ftwJiQAAAIC0ozgPAAAAIFMJCQnR2bNn7dovXLigkJAQJyQCAAAA0o7iPAAAAIBMxTAMmUwmu/bLly/Lw8PDCYkAAACAtHNzdgAAAAAASK1BgwbJZDJpyJAh8vLysrYnJSVpx44dqlixovPCAQAAAGlAcR7IRvZGN5KPj4+zYwAAADy0PXv2yDAM/f7778qRI4e1PUeOHKpQoYIGDBjgxHQAAABA6lGcBwAAAJBpLF++XP369dPUqVOZdAAAAIBMjeI8AAAAgExl9uzZzo4AAAAAPDKK8wAAAAAylStXrmjcuHFav369zpw5o+TkZJvtf/31l5OSAQAAAKlHcR4AAABApvLKK69o06ZN6tSpkwoUKCCTyeTsSAAAAECaUZwHAAAAkKmsXLlSK1asUM2aNZ0dBQAAAHhoLs4OAAAAAABp4efnpzx58jg7BgAAAPBIKM4DAAAAyFRGjhypoUOH6urVq86OAgAAADw0lrUBAAAAkKlMnDhRR44cUWBgoIKDg+Xu7m6zfefOnU5KhgcpO2y1XMxezo4BAJla3Lhmzo4AIJ1QnAcAAACQqbRq1crZEQAAAIBHRnEeAAAAQKYybNgwZ0cAAAAAHhlrzgMAAADIdOLj4/X5558rKipKFy5ckHR7OZtTp045ORkAAACQOsycBwAAAJCp7NmzRw0aNJCvr6/i4uLUs2dP5cmTR0uXLtXx48c1b948Z0cEAAAAHoiZ8wAAAAAylf79+6tr1646dOiQPDw8rO1NmzbV5s2bnZgMAAAASD2K8wAAAAAylV9++UURERF27YUKFdLp06edkAgAAABIO4rzAAAAADIVs9mshIQEu/aDBw/K39/fCYkAAACAtKM4DwAAACBTadmypUaMGKGbN29Kkkwmk44fP6533nlHL774opPTAQAAAKlDcR4AAABApjJx4kRdvnxZAQEBunbtmurUqaPixYsrV65cGj16tLPjAQAAAKni5uwAAAAAAJAWvr6+Wrt2rbZu3ao973xyVgABAABJREFUe/bo8uXLqlSpkho0aODsaAAAAECqUZwHAAAAkCnVqlVLtWrVcnYMAAAA4KFQnAcAAACQ6fzyyy/asGGDzpw5o+TkZJttkyZNclIqAAAAIPUozgMAAADIVMaMGaP33ntPpUqVUmBgoEwmk3Xb3f8GAAAAHmcU5wEAAABkKlOnTtWsWbPUtWtXZ0cBAAAAHpqLswMAAAAAQFq4uLioZs2azo4BAAAAPBKK8wAAAAAylTfffFOffPKJs2MAAAAAj4RlbQAAAABkKgMGDFCzZs0UGhqqJ598Uu7u7jbbly5d6qRkAAAAQOoxcx4AAABAptK3b19t2LBBJUuWVN68eeXr62vzyi6Cg4Nt1t3fuHGjTCaTNm7c6LRMAAAASD1mzgMAAADIVObOnaslS5aoWbNmzo4iSZozZ466desmSdqyZYtq1apls90wDBUpUkQnT55Us2bNtHz5cmfEBAAAwGOGmfMAAAAAMpU8efIoNDTU2THseHh4KDY21q5906ZNOnnypMxmc4aev3bt2rp27Zpq166doecBAABA+qA4DwAAACBTGT58uIYNG6arV686O4qNpk2batGiRbp165ZNe2xsrCpXrqz8+fNn6PldXFzk4eEhFxc+5gEAAGQG3LUBAAAAyFQ+/PBDrVy5UoGBgSpXrpwqVapk83KW9u3b6/z581q7dq217caNG1q8eLHCw8Pt+icnJ2vKlCkqU6aMPDw8FBgYqIiICF28eNGmn2EYGjVqlAoXLiwvLy/Vq1dP+/btszteSmvO/3td+jvq1q2runXr2u27cOFCRUdHq1ChQsqVK5fatGkji8WixMRERUZGKiAgQN7e3urWrZsSExPTPkgAAACwYs15AAAAAJlKq1atnB0hRcHBwapRo4YWLFigJk2aSJJWrlwpi8Widu3a6cMPP7TpHxERYV2vvm/fvjp69Kg+/vhj7dq1S9u2bZO7u7skaejQoRo1apSaNm2qpk2baufOnWrYsKFu3LiR7tcwduxYeXp66t1339Xhw4f10Ucfyd3dXS4uLrp48aKGDx+u7du3a86cOQoJCdHQoUPTPQMAAEB2QXEeAAAAQKYybNgwZ0e4p/DwcEVFRenatWvy9PRUTEyM6tSpo4IFC9r027p1qz7//HPFxMTYzKqvV6+eGjdurEWLFik8PFxnz57VhAkT1KxZM33//fcymUySpMGDB2vMmDHpnv/WrVvatGmT9RcDZ8+e1VdffaXGjRvrhx9+kCT16dNHhw8f1qxZs+5ZnE9MTLSZWZ+QkJDuWQEAADI7ivNANlJ22Gq5mL2cHQPpJG5cM2dHAADAqW7cuKEzZ84oOTnZpr1IkSJOSiS1bdtWkZGRWr58uRo3bqzly5fbzZiXpEWLFsnX11fPPfeczp07Z22vXLmyvL29tWHDBoWHh2vdunW6ceOG3njjDWthXpIiIyMzpDjfuXNna2FekqpVq6YFCxaoe/fuNv2qVaumDz/8ULdu3ZKbm/3HyrFjxyo6Ojrd8wEAAGQlFOcBAAAAZCoHDx5Ujx499OOPP9q0G4Yhk8mkpKQkJyWT/P391aBBA8XGxurq1atKSkpSmzZt7PodOnRIFotFAQEBKR7nzJkzkqRjx45JkkqUKGF3Hj8/v3ROb/+LDV9fX0lSUFCQXXtycrIsFovy5s1rd5yoqCj179/f+j4hIcHuGAAAANkdxXkAAAAAmUq3bt3k5uam5cuXq0CBAjYzyh8H4eHh6tmzp06fPq0mTZood+7cdn2Sk5MVEBCgmJiYFI/h7++fLlnuNTZJSUlydXW1a0+p7X7thmGk2G42m2U2m1OZEgAAIHuiOA8AAAAgU9m9e7f+7//+T6VLl3Z2lBS1bt1aERER2r59u77++usU+4SGhmrdunWqWbOmPD0973msokWLSro9075YsWLW9rNnz+rixYsPzOLn56f4+Hi79mPHjtkcDwAAAI7n4uwAAAAAAJAWTz75pM067Y8bb29vTZs2TcOHD1eLFi1S7NO2bVslJSVp5MiRdttu3bplLag3aNBA7u7u+uijj2xmqU+ZMiVVWUJDQ7V9+3bduHHD2rZ8+XKdOHEi9RcEAACADMHMeQAAAACZyvjx4/X2229rzJgxKleunM0DTCXJx8fHScn+p0uXLvfdXqdOHUVERGjs2LHavXu3GjZsKHd3dx06dEiLFi3S1KlT1aZNG/n7+2vAgAEaO3asmjdvrqZNm2rXrl1auXKl8uXL98Acr7zyihYvXqzGjRurbdu2OnLkiL788kuFhoam16UCAADgIVGcBwAAAJCpNGjQQJJUv359m/bH4YGwaTF9+nRVrlxZM2bM0KBBg+Tm5qbg4GB17NhRNWvWtPYbNWqUPDw8NH36dG3YsEHVqlXTmjVr1KxZsweeo1GjRpo4caImTZqkyMhIValSRcuXL9dbb72VkZcGAACAVDAZ93qCD4AsIyEhQb6+vgqKXCgXs5ez4yCdxI178AdyAACyijv3MxaLRbt27bpv3zp16jgoFVKL+1EASD98FgSc4+770fT6S01mzgMAAADIVCi+AwAAICugOJ+N1a1bV+fOndPevXvT7Zhdu3bVxo0bFRcXl27HvFvdunUlSRs3bsyQ4wMAACBziI+P1xdffKEDBw5IksqUKaPu3bvL19fXyckAAACA1HFxdgD8j8lkStWLwvSDBQcHW8fLxcVFuXPnVrly5fTqq69qx44dzo4HAACAR/Drr78qNDRUkydP1oULF3ThwgVNmjRJoaGh2rlzp7PjAQAAAKnCzPnHyPz5823ez5s3T2vXrrVrf+KJJxwZK01mzpyp5ORkZ8eQJFWsWNH6oKtLly7pwIEDWrRokWbOnKk333xTkyZNcnJCAAAAPIw333xTLVu21MyZM+Xmdvsjza1bt/TKK68oMjJSmzdvdnJCAAAA4MEozj9GOnbsaPN++/btWrt2rV3748zd3d3ZEawKFSpkN3bjx49XeHi4Jk+erBIlSqh3794OzXTlyhXlzJnToecEAADIan799Vebwrwkubm56e2331aVKlWcmAwAAABIPZa1yWSSk5M1ZcoUlSlTRh4eHgoMDFRERIQuXrxo13flypWqU6eOcuXKJR8fHz399NOKjY2167d//37Vq1dPXl5eKlSokCZMmGCzfePGjTKZTFq4cKFGjx6twoULy8PDQ/Xr19fhw4dt+nbt2lXBwcF2madOnapy5crJw8ND/v7+aty4sX799Vdrn9mzZ+vZZ59VQECAzGaznnzySU2bNu0RRiplnp6emj9/vvLkyaPRo0fLMAybnKkZ2+TkZA0fPlwFCxaUl5eX6tWrp/379ys4OFhdu3a19pszZ45MJpM2bdqkPn36KCAgQIULF7ZuX7lypcLCwpQzZ07lypVLzZo10759++wy//HHH2rTpo3y5MkjDw8PValSRd999126jw0AAEBm4ePjo+PHj9u1nzhxQrly5XJCIgAAACDtKM5nMhERERo4cKBq1qypqVOnqlu3boqJiVGjRo108+ZNa785c+aoWbNmunDhgqKiojRu3DhVrFhRq1atsjnexYsX1bhxY1WoUEETJ05U6dKl9c4772jlypV25x43bpyWLVumAQMGKCoqStu3b1eHDh0emLlHjx6KjIxUUFCQxo8fr3fffVceHh7avn27tc+0adNUtGhRDRo0SBMnTlRQUJD69OmjTz755BFGK2Xe3t5q3bq1Tp06pf3791vbUzu2UVFRio6OVpUqVfT++++rRIkSatSoka5cuZLi+fr06aP9+/dr6NChevfddyXdXsKoWbNm8vb21vjx4zVkyBDt379ftWrVsnmY7r59+1S9enUdOHBA7777riZOnKicOXOqVatWWrZsWbqPDQAAQGbw8ssvq0ePHvr666914sQJnThxQl999ZVeeeUVtW/f3tnxAAAAgFRhWZtMZOvWrfr8888VExOj8PBwa3u9evXUuHFjLVq0SOHh4bJYLOrbt6+qVq2qjRs3ysPDw9r37pnikvTf//5X8+bNU6dOnSTdLqQXLVpUX3zxhZo0aWLT9/r169q9e7dy5MghSfLz81O/fv20d+9elS1bNsXMGzZs0Jw5c9S3b19NnTrV2v7WW2/ZZNm0aZM8PT2t719//XU1btxYkyZN0muvvZbWoXqgO3mPHDmiMmXKpHps//nnH02aNMmuOB4dHa3hw4eneK48efJo/fr1cnV1lSRdvnxZffv21SuvvKLPPvvM2q9Lly4qVaqUxowZY23v16+fihQpol9++UVms1nS7WJ/rVq19M4776h169YpnjMxMVGJiYnW9wkJCQ8xSgAAAI+nDz74QCaTSZ07d9atW7ck3V5esXfv3ho3bpyT0wEAAACpw8z5TGTRokXy9fXVc889p3PnzllflStXlre3tzZs2CBJWrt2rS5dumSdoX43k8lk897b29tmXfYcOXKoatWq+uuvv+zO361bN2thXpLCwsIkKcW+dyxZskQmk0nDhg2z23Z3lrsL8xaLRefOnVOdOnX0119/yWKx3PP4D8vb21vS7QfFSqkf2/Xr1+vWrVvq06ePzfHeeOONe56rZ8+e1sK8dPvrEx8fr/bt29ucy9XVVdWqVbOe68KFC/rPf/6jtm3b6tKlS9Z+58+fV6NGjXTo0CGdOnUqxXOOHTtWvr6+1ldQUNDDDxYAAMBjJCkpSdu3b9fw4cN18eJF7d69W7t379aFCxc0efJk64QGAAAA4HHHzPlM5NChQ7JYLAoICEhx+5kzZyTdng0u6Z6z2e9WuHBhu4K9n5+f9uzZY9e3SJEidv0kpbje/R1HjhxRwYIFlSdPnvvm2LZtm4YNG6affvpJV69etdlmsVjk6+t73/3T6vLly5JkXZM0tWN77NgxSVLx4sVttufJk8c6Hv8WEhJi8/7QoUOSpGeffTbF/j4+PpKkw4cPyzAMDRkyREOGDLlnrkKFCtm1R0VFqX///tb3CQkJFOgBAECW4OrqqoYNG+rAgQMKCQlRuXLlnB0JAAAAeCgU5zOR5ORkBQQEKCYmJsXt/v7+aT7m3TO67/bv5W/S2jctjhw5ovr166t06dKaNGmSgoKClCNHDv3www+aPHmykpOTH+n4Kdm7d6+k/xXZM2Js77j7rwLunEu6ve58/vz57fq7ubnZ9BswYIAaNWqU4rH//UuCO8xmM7PGAABAllW2bFn99ddfdpMgAAAAgMyE4nwmEhoaqnXr1qlmzZp2Bd9/95NuF6DvVbx1lNDQUK1evVoXLly45+z577//XomJifruu+9sZuffWd4lvV2+fFnLli1TUFCQnnjiCWvO1Ixt0aJFJd2e1X73h8Hz58/f9y8I7nbn6xMQEKAGDRrcs1+xYsUk3V4/9X79AAAAsptRo0ZpwIABGjlypCpXrqycOXPabL/zl4gAAADA44w15zORtm3bKikpSSNHjrTbduvWLcXHx0uSGjZsqFy5cmns2LG6fv26Tb9HneWeVi+++KIMw1B0dLTdtjtZ7szIvzubxWLR7Nmz0z3PtWvX1KlTJ124cEGDBw+2LumT2rGtX7++3NzcNG3aNJs+H3/8caozNGrUSD4+PhozZoxu3rxpt/3s2bOSbhfv69atqxkzZujvv/++Zz8AAIDspmnTpvrtt9/UsmVLFS5cWH5+fvLz81Pu3LnvudQgAAAA8Lhh5nwmUqdOHUVERGjs2LHavXu3GjZsKHd3dx06dEiLFi3S1KlT1aZNG/n4+Gjy5Ml65ZVX9PTTTys8PFx+fn767bffdPXqVc2dO9dhmevVq6dOnTrpww8/1KFDh9S4cWMlJydry5Ytqlevnl5//XU1bNhQOXLkUIsWLRQREaHLly9r5syZCggISLEonVqnTp3Sl19+Ken2bPn9+/dr0aJFOn36tN566y1FRERY+6Z2bAMDA9WvXz9NnDhRLVu2VOPGjfXbb79p5cqVypcvn936/Snx8fHRtGnT1KlTJ1WqVEnt2rWTv7+/jh8/rhUrVqhmzZrWYv8nn3yiWrVqqVy5curZs6eKFSumf/75Rz/99JNOnjyp33777aHHBwAAILPKqL+wBAAAAByJ4nwmM336dFWuXFkzZszQoEGD5ObmpuDgYHXs2FE1a9a09uvRo4cCAgI0btw4jRw5Uu7u7ipdurTefPNNh2eePXu2ypcvry+++EIDBw6Ur6+vqlSpomeeeUaSVKpUKS1evFjvvfeeBgwYoPz586t3797y9/dX9+7dH/q8u3fvVqdOnWQymZQrVy4FBQWpRYsWeuWVV1S1alW7/qkd2/Hjx8vLy0szZ87UunXrVKNGDa1Zs0a1atWSh4dHqrKFh4erYMGCGjdunN5//30lJiaqUKFCCgsLU7du3az9nnzySf3666+Kjo7WnDlzdP78eQUEBOipp57S0KFDH3psAAAAMrM6deo4OwIAAADwyEyGo9c5AbKg+Ph4+fn5adSoURo8eLCz49hJSEiQr6+vgiIXysXs5ew4SCdx45o5OwIAAA7z448/qmbNmrJYLIqLi7tv3/LlyzsmFFKN+1EASD98FgSc4879jMViSbdnHDFzHkija9eu2T00dsqUKZKkunXrOj4QAABANlCrVi3rvytWrCiTyZTi85RMJpOSkpIcGQ1psDe6EQ/sBQAA+P8ozgNp9PXXX2vOnDlq2rSpvL29tXXrVi1YsEANGza0Wf4GAAAA6WfPnj0qV66cJOno0aNOTgMAAAA8OorzQBqVL19ebm5umjBhghISEqwPiR01apSzowEAAGRZRYoUsf47MDAw1c/6AQAAAB5XFOeBNKpUqZLWrVvn7BgAAADZVkBAgFq3bq2OHTuqfv36cnFxcXYkAAAAIM24i02FW7duacSIETp58qSzowAAAADZ3ty5c3X16lU9//zzKlSokCIjI/Xrr786OxYAAACQJhTnU8HNzU3vv/++bt265ewoAAAAQLbXunVrLVq0SP/884/GjBmj/fv3q3r16ipZsqRGjBjh7HgAAABAqlCcT6Vnn31WmzZtcnYMAAAAAP9frly51K1bN61Zs0Z79uxRzpw5FR0d7exYAAAAQKqw5nwqNWnSRO+++65+//13Va5cWTlz5rTZ3rJlSyclAwAAALKn69ev67vvvlNsbKxWrVqlwMBADRw40NmxAAAAgFShOJ9Kffr0kSRNmjTJbpvJZFJSUpKjIwEAAADZ0urVqxUbG6tvvvlGbm5uatOmjdasWaPatWs7OxoAAACQahTnUyk5OdnZEYBHtje6kXx8fJwdAwAA4JG0bt1azZs317x589S0aVO5u7s7OxIAAACQZhTnH8L169fl4eHh7BgAAABAtvTPP/8oV65czo4BAAAAPBKK86mUlJSkMWPGaPr06frnn3908OBBFStWTEOGDFFwcLB69Ojh7IgAAABAtpArVy4lJyfr8OHDOnPmjN1fubK8DQAAADIDivOpNHr0aM2dO1cTJkxQz549re1ly5bVlClTKM4DAAAADrJ9+3aFh4fr2LFjMgzDZhvPgwIAAEBm4eLsAJnFvHnz9Nlnn6lDhw5ydXW1tleoUEF//PGHE5MBAAAA2UuvXr1UpUoV7d27VxcuXNDFixetrwsXLjg7HgAAAJAqzJxPpVOnTql48eJ27cnJybp586YTEgEAAADZ06FDh7R48eIU788BAACAzIKZ86n05JNPasuWLXbtixcv1lNPPeWERAAAAED2VK1aNR0+fNjZMQAAAIBHwsz5VBo6dKi6dOmiU6dOKTk5WUuXLtWff/6pefPmafny5c6OBwAAAGQbb7zxht566y2dPn1a5cqVk7u7u8328uXLOykZAAAAkHom499PUMI9bdmyRSNGjNBvv/2my5cvq1KlSho6dKgaNmzo7GjAfSUkJMjX11cWi0U+Pj7OjgMAAJBmd9/P5M6d2267yWSSYRg8EPYxxf0oAADI7DLifoaZ82kQFhamtWvXOjsGAAAAkK0dPXrU2REAAACAR0ZxPg3i4+O1ePFi/fXXXxowYIDy5MmjnTt3KjAwUIUKFXJ2PAAAACBbKFq0qLMjAAAAAI+MB8Km0p49e1SyZEmNHz9e77//vuLj4yVJS5cuVVRUlHPDAQAAANnM/PnzVbNmTRUsWFDHjh2TJE2ZMkXffvutk5MBAAAAqUNxPpX69++vrl276tChQ/Lw8LC2N23aVJs3b3ZiMgAAACB7mTZtmvr376+mTZsqPj7eusZ87ty5NWXKFOeGAwAAAFKJ4nwq/fLLL4qIiLBrL1SokE6fPu2ERAAAAED29NFHH2nmzJkaPHiwXF1dre1VqlTR77//7sRkAAAAQOpRnE8ls9mshIQEu/aDBw/K39/fCYkAAACA7Ono0aN66qmn7NrNZrOuXLnihEQAAABA2lGcT6WWLVtqxIgRunnzpiTJZDLp+PHjeuedd/Tiiy86OR0AAACQfYSEhGj37t127atWrdITTzzh+EAAAADAQ3BzdoDMYuLEiWrTpo0CAgJ07do11alTR6dPn1aNGjU0evRoZ8cDAAAAso3+/fvrtdde0/Xr12UYhn7++WctWLBAY8eO1eeff+7seAAAAECqUJxPJV9fX61du1bbtm3Tb7/9psuXL6tSpUpq0KCBs6MBAAAA2corr7wiT09Pvffee7p69arCw8NVsGBBTZ06Ve3atXN2PAAAACBVTIZhGM4O8bi7efOmPD09tXv3bpUtW9bZcYA0S0hIkK+vrywWi3x8fJwdBwAAIM3udT9z9epVXb58WQEBAXb7bNu2TVWqVJHZbHZkVKSA+1EAAJDZZcT9DGvOp4K7u7uKFCmipKQkZ0cBAAAAcBcvL68UC/OS1KRJE506dcrBiQAAAIDUoTifSoMHD9agQYN04cIFZ0cBAAAAkAr8kTAAAAAeZ6w5n0off/yxDh8+rIIFC6po0aLKmTOnzfadO3c6KRkAAAAAAAAAILOhOJ9KrVq1cnYEAAAAAAAAAEAWQXE+lYYNG+bsCAAAAAAAAACALII15wEAAABkSSaTydkRAAAAgHti5nwqJSUlafLkyVq4cKGOHz+uGzdu2GznQbEAAADA44UHwgIAAOBxxsz5VIqOjtakSZP08ssvy2KxqH///nrhhRfk4uKi4cOHOzseAAAAgH+5dOmSihUr5uwYAAAAQIoozqdSTEyMZs6cqbfeektubm5q3769Pv/8cw0dOlTbt293djwAAAAg2/jnn3/UqVMnFSxYUG5ubnJ1dbV5AQAAAJkBy9qk0unTp1WuXDlJkre3tywWiySpefPmGjJkiDOjAQAAANlK165ddfz4cQ0ZMkQFChRgbXkAAABkShTnU6lw4cL6+++/VaRIEYWGhmrNmjWqVKmSfvnlF5nNZmfHAwAAALKNrVu3asuWLapYsaKzowAAAAAPjWVtUql169Zav369JOmNN97QkCFDVKJECXXu3Fndu3d3cjoAAAAg+wgKCuJhrwAAAMj0TAZ3tQ9l+/bt+vHHH1WiRAm1aNHC2XGA+0pISJCvr68sFot8fHycHQcAACDN7r6f2b59uyZOnKgZM2YoODjY2dGQCtyPAgCAzC4j7mcozqfS2LFjFRgYaDdLftasWTp79qzeeecdJyUDHuzOD4+gyIVyMXs5Ow4yibhxzZwdAQAAq7s/DBUtWlRXr17VrVu35OXlJXd3d5u+Fy5ccFJK3AvFeQAAkNllxP0Ma86n0owZMxQbG2vXXqZMGbVr147iPAAAAOAgU6ZMcXYEAAAA4JFRnE+l06dPq0CBAnbt/v7++vvvv52QCAAAAMieunTp4uwIAAAAwCOjOJ9KQUFB2rZtm0JCQmzat23bpoIFCzopFQAAAJA9JSUl6ZtvvtGBAwck3f6L1pYtW8rV1dXJyQAAAIDUoTifSj179lRkZKRu3rypZ599VpK0fv16vf3223rrrbecnA4AAADIPg4fPqymTZvq1KlTKlWqlKTbz4gKCgrSihUrFBoa6uSEAAAAwINRnE+lgQMH6vz58+rTp49u3LghSfLw8NA777yjqKgoJ6cDAAAAso++ffsqNDRU27dvV548eSRJ58+fV8eOHdW3b1+tWLHCyQkBAACAB6M4n0omk0njx4/XkCFDdODAAXl6eqpEiRIym83OjgYAAABkK5s2bbIpzEtS3rx5NW7cONWsWdOJyQAAAIDUozifRt7e3nr66aedHQMAAADItsxmsy5dumTXfvnyZeXIkcMJiQAAAIC0c3F2AAAAAABIi+bNm+vVV1/Vjh07ZBiGDMPQ9u3b1atXL7Vs2dLZ8QAAAIBUYeY8AAAAgEzlww8/VJcuXVSjRg25u7tLkm7duqWWLVtq6tSpTk6H+yk7bLVczF7OjgEAADKRuHHNnB0hwzBzHtlSXFycTCaTPvjgA4ecZ86cORl6HgAAgOwkd+7c+vbbb/Xnn39q8eLFWrx4sf78808tW7ZMvr6+zo4HAAAApArFeTjVnDlzZDKZZDKZtHXrVrvthmEoKChIJpNJzZs3d0LC1ImNjdWUKVOcHQMAACBbKVGihFq0aKEWLVqoePHizo4DAAAApAnL2uCx4OHhodjYWNWqVcumfdOmTTp58qTMZrOTkqVObGys9u7dq8jISJv2okWL6tq1a9Y/twYAAMDDGTRokPXf/fv3v2/fSZMmZXQcAAAA4JFRnMdjoWnTplq0aJE+/PBDubn979syNjZWlStX1rlz59LlPMnJybpx40a6HCs1TCaTPDw8HHY+AACArGrPnj3Wf+/atcuJSQAAAID0wbI2eCy0b99e58+f19q1a61tN27c0OLFixUeHm7X/4MPPtAzzzyjvHnzytPTU5UrV9bixYvt+plMJr3++uuKiYlRmTJlZDabtWrVqhQzGIahV199VTly5NDSpUut7V9++aUqV64sT09P5cmTR+3atdOJEyes2+vWrasVK1bo2LFj1iV6goODJaW85nzXrl3l7e2tU6dOqVWrVvL29pa/v78GDBigpKQkm0znz59Xp06d5OPjo9y5c6tLly767bffWMceAABkO8uXL7f+e8OGDfd9AQAAAJkBxXk8FoKDg1WjRg0tWLDA2rZy5UpZLBa1a9fOrv/UqVP11FNPacSIERozZozc3Nz00ksvacWKFXZ9//Of/+jNN9/Uyy+/rKlTp1oL53dLSkpS165dNW/ePC1btkwvvPCCJGn06NHq3LmzSpQooUmTJikyMlLr169X7dq1FR8fL0kaPHiwKlasqHz58mn+/PmaP3/+A9efT0pKUqNGjZQ3b1598MEHqlOnjiZOnKjPPvvM2ic5OVktWrTQggUL1KVLF40ePVp///23unTpkooRBQAAyLq6d++uS5cu2bVfuXJF3bt3d0IiAAAAIO1Y1gaPjfDwcEVFRenatWvy9PRUTEyM6tSpo4IFC9r1PXjwoDw9Pa3vX3/9dVWqVEmTJk1Ss2bNbPr++eef+v333/Xkk09a2+Li4qz/vnXrljp27KjvvvtO3333nRo2bChJOnbsmIYNG6ZRo0bZrHH6wgsv6KmnntKnn36qQYMG6bnnnlOhQoV08eJFdezYMVXXev36db388ssaMmSIJKlXr16qVKmSvvjiC/Xu3VuS9M033+inn37SlClT1K9fP0lS79699dxzzz3w+ImJiUpMTLS+T0hISFUuAACAzGDu3LkaN26ccuXKZdN+7do1zZs3T7NmzXJSMgAAACD1mDmPx0bbtm117do1LV++XJcuXdLy5ctTXNJGkk1h/uLFi7JYLAoLC9POnTvt+tapU8emMH+3Gzdu6KWXXtLy5cv1ww8/WAvzkrR06VIlJyerbdu2OnfunPWVP39+lShR4pH/ZLpXr14278PCwvTXX39Z369atUru7u7q2bOntc3FxUWvvfbaA489duxY+fr6Wl9BQUGPlBUAAOBxYbFYZBiGLl26pISEBOvr4sWL+uGHHxQQEODsiAAAAECqMHMejw1/f381aNBAsbGxunr1qpKSktSmTZsU+y5fvlyjRo3S7t27bWaIm0wmu74hISH3POfYsWN1+fJlrVy5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UUJPP/20JCk0NFSXL19OcaZ6WpQtW1ZPPfWUYmJiVLhwYR0/flwfffRResRPk6JFi0qSDh8+bDPL//z58/edCQ8AAID0x5rzAAAAAB57BQoUkCQdP35chmHo5MmTOn78eIqvtLozS37o0KHavXu39b0ktW3bVj/99JNWr15tt198fLxu3bqV6vN06tRJa9as0ZQpU5Q3b141adIkzVkfVf369eXm5qZp06bZtH/88ccOzwIAAJDdMXMeAAAAwGNvwIABioyMVIUKFWQymawz2+9mGIZMJpOSkpLSdOyQkBA988wz+vbbbyXJpjg/cOBAfffdd2revLm6du2qypUr68qVK/r999+1ePFixcXFKV++fKk6T3h4uN5++20tW7ZMvXv3lru7e5pypofAwED169dPEydOVMuWLdW4cWP99ttvWrlypfLly2fz4FcAAABkLIrzAAAAAB573bp1U2RkpLZt26ZnnnlG69atU968edPt+B06dNCPP/6oqlWr2jws1cvLS5s2bdKYMWO0aNEizZs3Tz4+PipZsqSio6PTtGZ8YGCgGjZsqB9++EGdOnVKt+xpNX78eHl5eWnmzJlat26datSooTVr1qhWrVry8PBwWi4AAIDsxmTwFB8gy0tISJCvr68sFot8fHycHQcAACDN7r6fWbZsmdq1ayez2ezsWGnWunVr/f777zp8+LCzo9iIj4+Xn5+fRo0apcGDB6f78e98/YIiF8rF7JXuxwcAAFlX3Lhmzo4gKWPqa6w5DwAAACBTefbZZ3X27Fnr+59//lmRkZH67LPPnJjqwf7++2+tWLHCqbPmJenatWt2bVOmTJEk1a1b17FhAAAAsjGWtQEAAACQqYSHh+vVV19Vp06ddPr0aTVo0EBly5ZVTEyMTp8+raFDhzo7oo2jR49q27Zt+vzzz+Xu7q6IiAi7PqdPn77vMTw9PdO0hM79fP3115ozZ46aNm0qb29vbd26VQsWLFDDhg1Vs2bNdDkHAAAAHoziPAAAAIBMZe/evapataokaeHChSpXrpy2bdumNWvWqFevXo9dcX7Tpk3q1q2bihQporlz5yp//vx2fQoUKHDfY3Tp0kVz5sxJlzzly5eXm5ubJkyYoISEBOtDYkeNGpUuxwcAAEDqUJwHAAAAkKncvHnTut78unXr1LJlS0lS6dKl9ffffzszWoq6du2q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Jzk5WVOmTFGZMmXk4eGhwMBARURE6OLFizbH+vXXX9WoUSPly5dPnp6eCgkJUffu3R84dgAAAAAAAAAeTxTnkW4GDx6sV199VZI0YsQIzZ8/XxEREZKk//znP6pdu7YSEhI0bNgwjRkzRvHx8Xr22Wf1888/3/e4RYsWVVJSkubPn//ADGvXrlXt2rW1f/9+9evXTxMnTlS9evW0fPny++43evRode7cWSVKlNCkSZMUGRmp9evXq3bt2nYPtL148aIaN26sChUqaOLEiSpdurTeeecdrVy50tonKSlJzZs3V3R0tCpXrqyJEyeqX79+slgs2rt3r7VfRESEBg4cqJo1a2rq1Knq1q2bYmJi1KhRI928eVPS7b9GaNiwoeLi4vTuu+/qo48+UocOHbR9+/YHjgcAAAAAAACAxxNreyDdPPfcczp16pQ+++wzNWnSRFWqVJEkGYahXr16qV69elq5cqV11npERITKlCmj9957T2vWrLnncbt3767Jkyera9euGjdunOrWravatWuradOm8vX1tfZLSkpSRESEChQooN27d9ssrWMYxj2Pf+zYMQ0bNkyjRo3SoEGDrO0vvPCCnnrqKX366ac27f/97381b948derUSZLUo0cPFS1aVF988YWaNGkiSZo3b57Wr1+vSZMm6c0337Tu++6771qzbN26VZ9//rliYmIUHh5u7VOvXj01btxYixYtUnh4uH788UddvHhRa9assY6pJI0aNeqe15SYmKjExETr+4SEhHv2BQAAAAAAAOB4zJxHhtu9e7cOHTqk8PBwnT9/XufOndO5c+d05coV1a9fX5s3b1ZycvI99w8MDNRvv/2mXr166eLFi5o+fbrCw8MVEBCgkSNHWovdu3bt0tGjRxUZGWm35n1Ky9jcsXTpUiUnJ6tt27bWbOfOnVP+/PlVokQJbdiwwaa/t7e3OnbsaH2fI0cOVa1aVX/99Ze1bcmSJcqXL5/eeOMNu/PdybJo0SL5+vrqueeeszlv5cqV5e3tbT3vnWtZvny5dTb9g4wdO1a+vr7WV1BQUKr2AwAAAAAAAOAYFOeR4Q4dOiRJ6tKli/z9/W1en3/+uRITE2WxWO57jAIFCmjatGn6+++/9eeff+rDDz+Uv7+/hg4dqi+++EKSrGu5ly1bNs35DMNQiRIl7PIdOHDA+pDbOwoXLmxX7Pfz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JMnLy0v+/v4WjQcAAAAAgGeF5DwAAC+gESNGqGfPnpKkcuXKWTgac/ny5dPOnTslSS4uLs91rpiYGAUHB0uSatWqlSI53717d9WvX1+SVLx48ecaCwAAADLPi3w9DADPCsl5AABeQMWKFVOxYsUsHUaqjEajfHx8LB2GJKlgwYIqWLCgpcMAAADAM/YiXw8DwLNCzXkAAF5AqdXYTH7v5eWlP/74QzVr1pSDg4NKliyplStXSpJWrlypMmXKyGg0qkKFCtq2bdtjx42IiNCoUaOUP39+2dvbq2bNmtq3b99TY3tSzfnbt29r/PjxqlixopycnOTo6KgyZcpo9OjRpj4//PCD2rVrp2LFiilHjhzKli2bPDw81L59e/3xxx9msRYuXNj0fseOHSnmfVIt0X379qldu3bKmzevsmXLprx586pt27b67bffnnqMAAAAsKzH1Zzftm2bmjZtqty5cytbtmzy9PSUv7+/jh8//sTxvvjiCxUtWlR2dnaqVKmSIiIinvMRAMDTsXIeAIAsJjY2VnXr1tWVK1ckSUePHlX79u01YsQIjRs3ztTvjz/+UMuWLXXmzBm5urqmGGfgwIE6evSo6f3OnTtVp04d/frrrxkqERMXF6datWrp999/N2s/fPiwbt68qZCQEEnSnj17TD8mJPv777+1YsUKbdiwQXv37lWpUqXSPf/D1q1bp7Zt2+revXumtosXL2rVqlVat26dVq5cqRYtWvyrOQAAAJC5ZsyYoQEDBigpKcnUdv78eS1cuFCrV6/W999/rypVqqTYb+rUqWaLQPbt26emTZvq+++/l6+vb6bEDgCpYeU8AABZTExMjIoVK6Z169apY8eOkqSkpCSNGzdOb731ltavX28qO3P9+nWFh4enOs65c+c0ffp0rV27VpUrV5b0IMEeGBiYobhGjBhhSsznzJlTU6dO1aZNm/TZZ5+pZMmSpn5Vq1bVZ599pnXr1ikyMlIRERGaOHGiJOnWrVuaOnWqabwVK1aY9nvttde0c+dO7dy5U5999tlj47h586Z69OhhSsz369dP3333nfr37y9Junfvnnr06KGbN29m6DgBAACQ+c6dO6d3331XSUlJsrKy0siRI7Vhwwa1a9dO0oPrXn9/f7PEfbJDhw4pJCRE69evl5+fn6QH14RDhgzJzEMAgBRYOQ8AQBb01VdfqVix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r6drLElPPVdP0759e+3Zs0fDhw/Xa6+9JicnJyUmJqpRo0YZuqshWYcOHfTRRx8pOjpa2bNn17p169SpUydT/Mljd+nSJUVt+mTJdfEfZTQaZTQaMxwbAADAq4DkPAAAAPCCq1y5siTp77//liR9++23io+P17p161SwYEFTv9TKqTzK29tbBw4cUL169VKsQn+UlZWV6tWrp3r16mnKlCkaP368RowYocjISFPiPa2aNm2qWrVqafz48erTp48cHR3l7e2trVu3qkaNGqnWLU/No4/MOnbsmCSlqLH+KG9vb0mSu7t7mmL39vbWe++9p/fee0/Hjx/Xa6+9pk8++USLFy9O91hp8bjP4tq1a/r+++8VHBys0aNHm9qTV++nZYzH6dChg4KDg7Vq1SrlyZNHcXFx6tixo2m7m5ubsmfProSEhGd2nAAAAPgfytoAAAAAL4jIyMgUyWdJ+u677yRJJUqUkPS/ldgP942NjdWCBQueOkf79u114cIFffnllym23b59Wzdv3pT0oJTKo1577TVJMnvQZ3p88MEHunLlimnu9u3bKyEhQWPHjk3R9/79+4qJiUnR/u2335r+jouL01dffaXXXnst1RXsD/Pz85Ozs7PGjx+ve/fupdh++fJlSdKtW7d0584ds23e3t7Knj276bjTOlZ6ODg8eEjqo8ec2mctSdOmTUsxhqOjY6pjPE6pUqVUrlw5LVu2TMuWLVO+fPlUs2ZNs7nbtGmjVatW6eDBgyn2z8hxAgAA4H9YOQ8AAAC8IAYOHKhbt26pVatWKlmypO7evas9e/Zo2bJl8vLyMtX5btiwobJly6bmzZurT58+unHjhr788ku5u7ubVtc/TteuXbV8+XL17dtXkZGRqlGjhhISEvTXX39p+fLl2rx5sypXrqyQkBD98MMPatq0qQoVKqRLly5pxowZKlCggHx8fDJ0fI0bN1bZsmU1ZcoU/ec//1GtWrXUp08fhYaG6vfff1fDhg1la2ur48ePa8WKFZo+fbratm1rNsaAAQN06NAh5cmTR/Pnz9fFixfT9KOEs7OzZs6cqa5du6pixYrq2LGj3NzcdPbsWW3YsEE1atTQ559/rmPHjqlevXpq3769SpcuLRsbG61Zs0YXL140rSpP61jpYW9vr9KlS2vZsmUqXry4cubMqbJly6ps2bKmuvf37t1T/vz5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QkND5eLiYno9/AMGAAAAMia5ZKHBYNCuXbtSbE9KSpKnp6cMBoOaNWtmgQgBAACQlbByHhb19ttva+rUqQoPD9eHH36o8+fPa+fOnRo0aJCsra11/Phx/fHHH49dqf5ovfrChQun6GNlZaW3335bM2fO1K1bt+Tg4KAlS5bIzs5O7dq1S3fMuXPnVv369VO029g8/T+n5IR60aJFzdpz5swpV1fXVPd5dGV/cr9r1649dp7AwEANHTrU9D4uLo4EPQAAwDNiZ2en8PBw+fj4mLXv2LFD58+fl9FotFBkAAAAyEpYOQ+LqlSpkkqWLKmlS5dKSlkHPjExUQ0aNEh1pXpERITatGljNp69vX2q87zzzju6ceOG1q5dq6SkJIWHh6tZs2aPLQvzInm4Tv7DkpKSHruP0WiUs7Oz2QsAAADPRpMmTbRixQrdv3/frD08PFyVKlVS3rx5LRSZZdy8edPSIQAAAGRJJOdhcW+//bapzEx4eLiKFSumKlWqSJK8vb1148YN1a9fP9VXWuvFly1bVq+//rqWLFminTt36uzZs+ratevzPKxUFSpUSJJ04sQJs/YrV648cSU8AAAAXhydOnXSlStXFBERYWq7e/euVq5cqc6dO6foP3nyZFWvXl25cuWSvb29KlWqpJUrV6boZzAYNGDAAK1du1Zly5aV0WhUmTJltGnTJrN+Z86cUf/+/VWiRAnZ29srV65cateunVmpyGR//PGHatWqJXt7exUoUEDjxo3TggULZDAYUvTfuHGjfH195ejoqOzZs6tp06Y6dOiQWR9/f385OTnp5MmTatKkibJnz25aWAMAAID0ITkPi0u+mB89erR+//13s4v79u3b68cff9TmzZtT7BcTE5NitdKTdO3aVVu2bNG0adOUK1cuNW7c+N8Hn0716tWTjY2NZs6cadb++eefZ3osAAAAyBgvLy+9+eabprs/pQeJ7djYWHXs2DFF/+nTp+v1119XSEiIxo8fLxsbG7Vr104bNmxI0XfXrl3q37+/OnbsqEmTJunOnTtq06aNrly5Yurz66+/as+ePerYsaM+/fRT9e3bV99//71q166tW7dumfpduHBBderU0aFDhxQYGKh3331XS5Ys0fTp01PMu2jRIjVt2lROTk6aOHGiRo0apcOHD8vHxydFEv/+/fvy8/OTu7u7Jk+enOJuVkmK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rbt371rd1NXefH195e3trcOHDydrv0OHDuno0aP65ptv1K5dO7N948aNKV0iAAAAEsGyNgAAAMAzJi5kfnB29e7du7Vr1654+y9fvlxhYWHm419//VW7d+9WvXr1JEk5cuRQmTJl9M033ygiIsLsd/jwYW3YsEH169d/rJokadKkSTZ944L+B59Lkvk8D+8Td9PaBg0aPLKOOG3bttXVq1fVpUsXXb9+XW+88UaS942Ps7OzXn31VS1btizesPuff/4xv3/11VcVHh6uqVOn2vRL7CasKc3JyUlNmjTRqlWrtGfPniTXEt/P0jAMff7550+nUAAAAMSLmfMAAACAA/znP//RunXrbNp79eqlhg0b6rvvvlPTpk3VoEEDnTx5UjNmzFCxYsV0/fp1m30KFiyoqlWrqmvXroqOjtakSZOUJUsWDRgwwOzz6aefql69eqpUqZLeeust3bp1S1OmTJGPj4+GDRv2yHq9vb1VrVo1jRs3Tnfv3lWuXLm0YcMGnTx50qZv+fLlJUmDBg1S69at5erqqkaNGql06dJq3769Zs6cqYiICAUFBenXX3/VN998oyZNmqhGjRpJPn9ly5ZViRIltGTJEhUtWlTlypVL8r4J+eSTT7R582ZVrFhRnTp1UrFixXTlyhXt3btXmzZt0pUrVyTdX/P+22+/VZ8+ffTrr78qMDBQN27c0KZNm9StWzc1btz4iWtJqtGjR2vDhg0KCgpS586dVbRoUZ0/f15LlizR9u3blTFjRpt9ihQpogIFCqhfv34KCwuTt7e3li1bluga8gAAAEh5hPMAAACAA0yfPj3e9g4dOqhDhw66cOGCvvzyS61fv17FihXTvHnztGTJEm3ZssVmn3bt2snJyUmTJk3SpUuXVKFCBU2dOlU5cuQw+9SqVUvr1q3T0KFDNWTIELm6uiooKEhjx45N8MarD1uwYIF69OihadOmyTAM1alTR2vXrlXOnDmt+r300ksaOXKkZsyYoXXr1ik2NlYnT55U+vTpNWvWLOXPn19z5szR999/Lz8/Pw0cODDBJXsS065dOw0YMOCJbgT7oOzZs+vXX3/ViBEj9N133+mLL75QlixZVLx4cY0dO9bs5+zsrDVr1ujjjz/WggULtGzZMmXJkkVVq1ZVyZIlU6SWpMqVK5d2796tjz76SPPnz1dUVJRy5cqlevXqydPTM959XF1dtWrVKvXs2VNjxoyRh4eHmjZtqu7du6t06dJ2rR8AACAtsxj2/NwlAIeIioqSj4+PIiMj5e3t7ehyAAAAki2+65nPP/9c7733nkJDQ+Xv7+/gCpGYuJ9fnt6L5eQe/z8aAADgaKGfJH2JPaQ9TyNfY815AAAAAM8dwzD09ddfKygoiGAeAAAAzyWWtQEAAADw3Lhx44ZWr16tzZs369ChQ1qxYoWjSwIAAAAeC+E8AAAAgOdGeHi4Xn/9dWXMmFEffvihQkJCHF0SAAAA8FgI5wEAAAA8NwICAsRts55fh4cHcw8kAACA/8ea8wAAAAAAAAAA2BnhPAAAAAAAAAAAdkY4DwAAAAAAAACAnRHOAwAAAAAAAABgZ4TzAAAAAAAAAADYGeE8AAAAAAAAAAB2RjgPAAAAAAAAAICdEc4DAAAAAAAAAGBnhPMAAAAAAAAAANgZ4TwAAAAAAAAAAHZGOA8AAAAAAAAAgJ0RzgMAAAAAAAAAYGeE8wAAAAAAAAAA2BnhPAAAAAAAAAAAdkY4DwAAAAAAAACAnRHOAwAAAAAAAABgZ4TzAAAAAAAAAADYGeE8AAAAAAAAAAB2RjgPAAAAAAAAAICdEc4DAAAAAAAAAGBnhPMAAAAAAAAAANiZi6MLAAAAAACkDSWGrpeTu6ejywAAIE0J/aSBo0tAApg5DwAAAAAAAACAnRHOAwAAAAAAAABgZyxrA6QhfIwYAACkND4mDQAAADweZs4DAAAASDM6dOggLy8vR5chSQoNDZXFYtGcOXMc8vxbtmyRxWLRli1bHPL8AAAAaR0z5wEAAIA04PqhTbq8ZtK/DRYnOafPKI+8ZZWxWlu5ZMjqsNqeJ7GxsZo3b56mTZumY8eO6e7du8qRI4defvlldevWTS+//LKjS7TxxRdfyNPTUx06dEiR440ePVrFihVTkyZNUuR4AAAAaRXhPAAAAJCG+FRtI5eMfjLu3dGdc3/p+qFNij57RDnfmiaLi5ujy3vm9ezZU9OmTVPjxo3Vpk0bubi46K+//tLatWuVP3/+ZIXzAQEBunXrllxdXZ9ixffD+axZs9qE89WqVdOtW7fk5pa8n/vo0aPVvHlzwnkAAIAnRDgPAAAApCHp8r8o9xyF7j8oHSyndN6K2r1UN4/tVvqigY4t7jHdvn1bbm5ucnJ6uqt2Xrx4UV988YU6deqkmTNnWm2bNGmS/vnnn2Qdz2KxyMPDIyVLTBYnJyeHPj8AAEBax5rzAAAAQBrmnqe4JOlexHmr9ruXz+if70frzOetdeqzpjr/TW/dPLbbqo8Rc0/Dhw9XoUKF5OHhoSxZsqhq1arauHGjVb8///xTzZs3V+bMmeXh4aEXX3xRK1eutOpz5coV9evXTyVLlpSXl5e8vb1Vr149HThwwKrftm3bZLFY9N///leDBw9Wrly55OnpqaioKEnS7t27Vb9+fWXKlEnp06dXqVKl9Pnnn9uMOywsTE2aNJGXl5d8fX3Vr18/xcTEJHquTp48KcMwVKVKFZttFotF2bJls2qLiIjQe++9p7x588rd3V25c+dWu3btFB4eLinhNeeTcr7mzJkji8WiHTt2qE+fPvL19VX69OnVtGlTq38kyJs3r37//Xf9/PPPslgsslgsql69uqT415w/duyYXn31Vfn5+cnDw0O5c+dW69atFRkZaY7zxo0b+uabb8zjpdRyOQAAAGkNM+cBAACANCwm8qIkycnj35uk3vnnlC7MHyAXryzyfrm5nFw9dOPP7frnu1HybTpQnoUrS5IidizQ8F+W6O2331aFChUUFRWlPXv2aO/evapdu7Yk6ffff1eVKlWUK1cuffDBB0qfPr0WL16sJk2aaNmyZWratKkk6e+//9by5cvVokUL5cuXTxcvXtSXX36poKAgHTlyxOYmriNHjpSbm5v69eun6Ohoubm5aePGjWrYsKFy5MihXr16yc/PT3/88Yd++OEH9erV698xx8QoODhYFStW1GeffaZNmzZp/PjxKlCggLp27ZrguQoICJAkLVmyRC1atJCnp2eCfa9fv67AwED98ccfevPNN1WuXDmFh4dr5cqVOnv2rLJmjX+N/6Serzg9evRQpkyZNHToUIWGhmrSpEnq3r27Fi1aJOn+jP4ePXrIy8tLgwYNkiRlz5493ue+c+eOgoODFR0drR49esjPz09hYWH64YcfFBERIR8fH82dO9f8eXfu3FmSVKBAgQTPAwAAABJGOA8AAACkIbHRNxRzM1LGvbuKPv+XInYslJxdla5ABbPP1R9nysXbVznaTZTF5f566F5lG+ji/AG6umWOGc7fOvGb6tevb7PEy4N69eolf39//fbbb3J3d5ckdevWTVWrVtX7779vhs0lS5bU0aNHrZam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69atJfE7IE5ae//2tMR3HiVej8mRVt9bP+tY1gZIpdKlS6fo6Gib9rjlEdKlS2fvkuwiblxJGfvzeI4uXLigBg0ayMfHR0uXLpWzs7Ok1D3uIkWKqFatWmrXrp1++OEHXb9+XY0aNZJhGKl63IMHD1bmzJnVo0ePBPs8avwPjul5G/+DChYsqMaNG2vz5s2KiYlJleOOq+O1116zan/99dclSbt27UqV437Y9evXtWLFCgUHBytLlixme2oc+3//+1917txZs2bNUqdOndSsWTN9/fXXat++vd5//31dvnw5VY4baQuvy5TxJH8H8a/UfN34LHjvvffk5ORk9YlPzmPafP/2NCR0HhPC6zF+afW99bOOcB5IpXLkyGF+LOlBcW05c+a0d0l2EfcxqoTGnjlzZvNfeHPkyKELFy7IMAybftKzd44iIyNVr149RUREaN26dVb1peZxP6x58+b67bffdPTo0VQ77mPHjmnmzJnq2bOnzp07p9DQUIWGhur27du6e/euQkNDdeXKlUeO/+HXyPP8OyFPnjy6c+eObty4kSrHHVdH9uzZrdqzZcsmSbp69WqqHPfDli9frps3b1otaSM9+nfc8zj2L774QmXLllXu3Lmt2kNCQnTz5k3t27cvVY4baQuvy5TzuH8H8a/Uet34rEiXLp2yZMmiK1eumG1p/Tzy/i1lJHYeE8LrMWnSwnvr5wHhPJBKlSlTRkePHlVUVJRV++7du83tqVGuXLnk6+trddOsOL/++qvVuMuUKaObN2/qjz/+sOr3LJ6j27dvq1GjRjp69Kh++OEHFStWzGp7ah13fOI+IhcZGZlqxx0WFqbY2Fj17NlT+fLlM792796to0ePKl++fBoxYoRKlCghFxcXm/HfuXNH+/fvtxn/8/w74e+//5aHh4e8vLxS5bjLly8v6f7P/kFx6zX6+vqmynE/bP78+fLy8lJISIhVe2oc+8WLFxUTE2PTfvfuXUnSvXv3UuW4kbbwukw5j/t3EP9KrdeNz4pr164pPDzcajnGtHweef+WMh51HhPC6zFp0sJ76+eCASBV+uWXXwxJxqeffmq23b592yhYsKBRsWJFB1aWMn777TdDkjF79mybbe+8846RLl064/Tp02bbpk2bDEnG9OnTzbYzZ84Yrq6uxrvvvmu2xcbGGoGBgUauXLmMe/fuPdUxJNW9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zymnnBJDhgyJ5cuXx9577x0REU899VT87ne/i9/+9rdZrg4AgOpOOM96mzZtWvTt2zeWLFkS3377bTRu3Di++uqrqFevXjRr1kw4DwBAhXDeeefF119/HaeffnpmQUmdOnXi/PPPj6FDh2a5OgAAqju3tWG9nX322XHggQfGggULom7duvHSSy/FjBkzYscdd4yrrroq2+UBAEBEROTk5MQVV1wR8+bNi5deeineeOONmD9/flx88cXZLg0AAKycZ/29/vrrMW7cuKhRo0bUrFkzioqKYrPNNosrr7wyBg0aFIcccki2SwQAgIwGDRrEzjvvnO0yAACgBCvnWW+1atWKGjW+P3WaNWsWM2fOjIiIgoKCmDVrVjZLAwAAAACoFITzrLeuXbvGq6++GhERPXv2jIsvvjjuueeeGDJkSHTu3DnL1aWjXbt2cfzxx2eeP/PMM5GTkxPPPPNM1moCAAAAACoP4TzrbfTo0dGyZcuIiBg1alQ0atQoTjvttPjqq69i3LhxqdYyYcKEyMnJiZycnPj3v/9danuSJNG6devIycmJAw44INXaAAAAAADWxD3nWW+dOnWKJEki4vvb2owdOzYeeOCB2GabbaJLly5ZqalOnToxceLE2H333Uu0P/vss/HZZ59FXl5eub7+nnvuGUuXLo3atWuX6+sAAAAAAFWDlfOst4MOOijuuuuuiIhYuHBh7LLLLnHNNdfEwQcfHGPGjMlKTX379o37778/VqxYUaJ94sSJseOOO0aLFi3K9fVr1KgRderUydyLHwAAAADgp0gSWW9Tp06NPfbYIyIiJk+eHM2bN48ZM2bEXXfdFTfccENWaho4cGB8/fXXMWXKlEzbsmXLYvLkyXH00UeX6l9cXBzXXXdddOrUKerUqRPNmzePX/3qV7FgwYIS/ZIkiUsvvTRatWoV9erVi7322iv++9//ltrf6u45/+P70q/Sq1ev6NWrV6nfve+++2L48OGx6aabRsOGDeOwww6LRYsWRVFRUQwZMiSaNWsWDRo0iBNOOCGKiorWf5AAAAAAgArDbW1Yb0uWLImGDRtGRMQTTzwRhxxySNSoUSN22WWXmDFjRlZqateuXfTo0SMmTZoU+++/f0REPProo7Fo0aI46qijSv2jwa9+9auYMGFCnHDCCTF48OD49NNP409/+lNMmzYtnn/++ahVq1ZERFx88cVx6aWXRt++faNv374xderU2G+//WLZsmVlfgyXXXZZ1K1bN37/+9/HRx99FDfeeGPUqlUratSoEQsWLIhLLrkkXnrppZgwYUK0b98+Lr744jKvAQAAAABIh3Ce9daxY8d48MEHY8CAAfH444/H2WefHRERX375ZeTn52etrqOPPjqGDh0aS5cujbp168Y999wTPXv2jE022aREv3//+99x6623xj333FNiVf1ee+0Vffr0ifvvvz+OPvromDdvXlx55ZXRr1+/+Mc//hE5OTkREXHhhRfG6NGjy7z+FStWxLPPPpv5h4F58+bFX/7yl+jTp0/83//9X0REnH766fHRRx/F7bff/pPhfFFRUYnV9YWFhWVeLwAAAADw87mtDevt4osvjnPPPTfatWsX3bt3jx49ekTE96vou3btmrW6jjjiiFi6dGk8/PDD8c0338TDDz+82lva3H///VFQUBD77rtvfPXVV5nHjjvuGA0aNIinn346IiKefPLJWLZsWZx11lmZYD4iYsiQIeVS/3HHHZcJ5iMiunfvHkmSxIknnliiX/fu3WPWrFml7q//Q5dddlkUFBRkHq1bty6XmgEAAACAn8fKedbbYYcdFrvvvnvMmTMntt9++0z7L37xixgwYEDW6mratGnss88+MXHixFiyZEmsXLkyDjvssFL9Pvzww1i0aFE0a9Zstfv58ssvIyIyt+jZfPPNS71Oo0aNyrj6iDZt2pR4XlBQEBFRKlgvKCiI4uLiWLRoUTRp0mS1+xo6dGicc845meeFhYUCegAAAACoQITz/CwtWrSIFi1alGjr1q1blqr5n6OPPjpOOeWUmDt3buy///6x0UYblepTXFwczZo1i3vuuWe1+2jatGmZ1PLD1fY/tHLlyqhZs2ap9tW1/VR7kiRrfO28vLzIy8tbhyoBAAAAgGwQzlOlDBgwIH71q1/FSy+9FPfee+9q+3To0CGefPLJ2G233aJu3bpr3Ffbtm0j4vuV9ptttlmmfd68ebFgwYK11tKoUaNYuHBhqfYZM2aU2B8AAAAAUP245zxVSoMGDWLMmDFxySWXxIEHHrjaPkcccUSsXLkyRo4cWWrbihUrMoH6PvvsE7Vq1Yobb7yxxCr16667bp1q6dChQ7z00kuxbNmyTNvDDz8cs2bNWvcDAgAAAACqJCvnqXIGDRr0k9t79uwZv/rVr+Kyyy6L119/Pfbbb7+oVatWfPjhh3H//ffH9ddfH4cddlg0bdo0zj333LjsssvigAMOiL59+8a0adPi0UcfjY033nitdZx88skxefLk6NOnTxxxxBHx8ccfx5///Ofo0KFDWR0qAAAAAFBJWTlPtTR27NgYP358fPnll3HBBRfE0KFD45///Gf88pe/jN122y3T79JLL43hw4fHtGnT4rzzzouPP/44nnjiiahfv/5aX6N3795x9dVXxwcffBBDhgyJF198MR5++OFo1apVeR4aAAAAAFAJ5CQ/9a2SQJVQWFgYBQUF0XrIfVEjr162ywH+v+mX98t2CQCVxqr5zKJFiyI/Pz/b5bCe/P0AgMquPOYzVs4DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACnLzXYBQHreHt478vPzs10GAAAAAFR7Vs4DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApy812AQAAAFQPnYc9HjXy6mW7DACgCpl+eb9sl/CzWTkPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkLDfbBQDp6Tzs8aiRVy/bZQAAVcj0y/tluwQAAKiUrJwHAACowiZMmBA5OTkxffr0Mtvn8ccfH+3atSuz/QEAVEfCeQAAgDKyKgjPycmJf//736W2J0kSrVu3jpycnDjggAOyUCEAABWFcB4AAKCM1alTJyZOnFiq/dlnn43PPvss8vLyUqvl2GOPjaVLl0bbtm1Te00AANZOOA8AAFDG+vbtG/fff3+sWLGiRPvEiRNjxx13jBYtWpTJ6xQXF8d333232m3ffvttRETUrFkz6tSpEzk5OWXymgAAlA3hPAAAQBkbOHBgfP311zFlypRM27Jly2Ly5Mlx9NFHl+p/1VVXxa677hpNmjSJunXrxo477hiTJ08u1S8nJyfOPPPMuOeee6JTp06Rl5cXjz32WOZ2Os8++2ycfvrp0axZs2jVqlVErPme848++mjsscceUb9+/WjYsGH069cv/vvf/5Z6zQcffDA6d+4cderUic6dO8cDDzywgaMDAECEcB4AAKDMtWvXLnr06BGTJk3KtD366KOxaNGiOOqoo0r1v/7666Nr164xYsSIGD16dOTm5sbhhx8ejzzySKm+//znP+Pss8+OI488Mq6//voSX8x6+umnxzvvvBMXX3xx/P73v19jfXfffXf069cvGjRoEFdccUVcdNFF8c4778Tuu+9eIsR/4okn4tBDD42cnJy47LLL4uCDD44TTjghXnvttZ83MAAAZORmuwAAAICq6Oijj46hQ4fG0qVLo27dunHPPfdEz549Y5NNNinV94MPPoi6detmnp955pmxww47xDXXXBP9+vUr0ff999+Pt956K7bZZptM2+uvvx4REY0bN46nnnoqatasuca6Fi9eHIMHD46TTz45xo8fn2kfNGhQbLnlljF69OhM+/nnnx/NmzePf//731FQUBARET179oz99tvvJ+9hX1RUFEVFRZnnhYWFa+wLAFBdWTkPAABQDo444ohYunRpPPzww/HNN9/Eww8/vNpb2kREiWB+wYIFsWjRothjjz1i6tSppfr27NmzRDD/Q6eccspPBvMREVOmTImFCxfGwIED46uvvso8atasGd27d4+nn346IiLmzJkTr7/+egwaNCgTzEdE7Lvvvmt8/VUuu+yyKCgoyDxat279k/0BAKojK+cBAADKQdOmTWOfffaJiRMnxpIlS2LlypVx2GGHrbbvww8/HJdeemm8/vrrJVacr+5LXNu3b7/G1/ypbat8+OGHERGx9957r3Z7fn5+RETMmDEjIiI233zzUn223HLL1f7DwSpDhw6Nc845J/O8sLBQQA8A8CPCeQAAgHJy9NFHxymnnBJz586N/fffPzbaaKNSfZ577rno379/7LnnnnHzzTdHy5Yto1atWnHHHXfExIkTS/X/4Sr79dm2SnFxcUR8f9/5Fi1alNqem7vhl4l5eXmRl5e3wfsBAKjKhPMAAADlZMCAAfGrX/0qXnrppbj33ntX2+evf/1r1KlTJx5//PESgfYdd9xRLjV16NAhIiKaNWsW++yzzxr7rbqn/KqV9j/0/vvvl0ttAADViXvOAwAAlJMGDRrEmDFj4pJLLokDDzxwtX1q1qwZOTk5sXLlykzb9OnT48EHHyyXmnr37h35+fkxevToWL58eant8+bNi4iIli1bRpcuXeLOO++MRYsWZbZPmTIl3nnnnXKpDQCgOrFyHgAAoBwNGjToJ7f369cvrrnmmujTp08cffTR8eWXX8ZNN90UHTt2jDfffLPM68nPz48xY8bEscceGzvssEMcddRR0bRp05g5c2Y88sgjsdtuu8Wf/vSniPj+i1379esXu+++e5x44okxf/78uPHGG6NTp06xePHiMq8NAKA6sXIeAAAgi/bee++47bbbYu7cuTFkyJCYNGlSXHHFFTFgwIBye82jjz46nnrqqdh0003jj3/8Y/zmN7+Jv/zlL9GlS5c44YQTMv369OkT999/f6xcuTKGDh0af/vb3+KOO+6InXbaqdxqAwCoLnKSJEmyXQRQvgoLC6OgoCBaD7kvauTVy3Y5AEAVMv3yfqm8zqr5zKJFiyI/Pz+V16TsmI8CAOWlMs9HrZwHAAAAAICUCeehnLVr1y6OP/74n/27BxxwQNkWBAAAAABknXAe1tOECRMiJycnXnvttdVu79WrV3Tu3DnlqgAAAACAyiQ32wVAVff+++9HjRr+HQwAAAAA+B/hPJSzvLy8bJcAAAAAAFQwlvNCOVvdPefffPPN6NmzZ9StWzdatWoVl156adxxxx2Rk5MT06dPL7WPf//739GtW7eoU6dObLbZZnHXXXelUzwAAAAAUC6snIefadGiRfHVV1+Val++fPlP/t7s2bNjr732ipycnBg6dGjUr18/br311jWusP/oo4/isMMOi5NOOikGDRoUt99+exx//PGx4447RqdOncrkWAAAAACAdAnn4WfaZ5991rjtp0LzK664IhYsWBBTp06NLl26RETECSecEJtvvvlq+7///vvxr3/9K/bYY4+IiDjiiCOidevWcccdd8RVV1212t8pKiqKoqKizPPCwsK1HQ4AAAAAkCLhPPxMN910U2yxxRal2n/729/GypUr1/h7jz32WPTo0SMTzEdENG7cOI455pi48cYbS/XfZpttMsF8RETTpk1jyy23jE8++WSNr3HZZZfF8OHD1/FIAAAAAIC0CefhZ+rWrVvstNNOpdobNWq02tvdrDJjxozo0aNHqfaOHTuutn+bNm1W+xoLFixY42sMHTo0zjnnnMzzwsLCaN269Rr7AwAAAADpEs5DBVezZs3VtidJssbfycvLW+M97AEAAACA7KuR7QKgumnbtm189NFHpdpX1wYAAAAAVE3CeUhZ796948UXX4zXX3890zZ//vy45557slcUAAAAAJAq4Tyk7He/+10UFBTEvvvuGyNGjIirr746dtttt8y95XNycrJcIQAAAABQ3oTzkLLWrVvH008/HVtvvXWMHj06rrvuuhg0aFCceOKJERFRp06dLFcIAAAAAJQ3XwgL6+n444+P448/fo3bn3nmmRLPp0+fXqpPly5d4l//+leJtiFDhkSdOnVi4403/snfXd1rAAAAAACVi5XzkAVLly4t8fzrr7+Ou+++O3bfffeoWbNmlqoCAAAAANJi5TxkQY8ePaJXr16x9dZbxxdffBG33XZbFBYWxkUXXZTt0gAAAACAFAjnIQv69u0bkydPjvHjx0dOTk7ssMMOcdttt8Wee+6Z7dIAAAAAgBQI5yELRo8eHaNHj852GQAAAABAlrjnPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkLDfbBQAAAFA9vD28d+Tn52e7DACACsHKeQAAAAAASJlwHgAAAAAAUiacBwAAAACAlAnnAQAAAAAgZcJ5AAAAAABImXAeAAAAAABSJpwHAAAAAICU5Wa7ACA9bw/vHfn5+dkuAwAAAACqPSvnAQAAAAAgZcJ5AAAAAABImXAeAAAAAABSJpwHAAAAAICUCecBAAAAACBlwnkAAAAAAEiZcB4AAAAAAFImnAcAAAAAgJQJ5wEAAAAA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k3z66adJklT9MTj//POTiCix4mxVe40aNZLFixdX+TGg4nI+rZ25bNkwD94w1XEOvSGq8/x7Q1T3ufuGMO8vexXpmsE956GKmjZtWmyxxRaRn59for1bt24REfH6669noar0zJ49O7788svYaaedSm3r1q1bTJs2LfN82rRpUb9+/dh6661L9Vu1vaJLkiS++OKL2HjjjSOi+hz/t99+G1999VV8/PHHce2118ajjz4av/jFLyKieozBypUr46yzzoqTTz45tt1221Lb33rrrVixYkWpMahdu3Z06dKl1BhU1veME044IfLz86NOnTqx1157xWuvvZbZVpXH4Mknn4z8/PyYPXt2bLnlltGgQYPIz8+P0047Lb777ruIqNrHvzrLly+P++67L3bddddo165dRFT9MejVq1dERJx00knx+uuvx6xZs+Lee++NMWPGxODBg6N+/fpVfgyouJxPP191mMeUleo6D94Q1X0OvSHMvzdcdZ27bwjz/rJV0a4ZhPNQRc2ZMydatmxZqn1V2+eff552SamaM2dORMQax2D+/PlRVFSU6du8efPIyckp1S+icozVPffcE7Nnz44jjzwyIqrP8f/2t7+Npk2bRseOHePcc8+NAQMGxJ/+9KeIqB5jMHbs2JgxY0aMHDlytdvXNgY/PK7K+J5Ru3btOPTQQ+P666+Pv//973HppZfGW2+9FXvssUdm8lSVx+DDDz+MFStWxEEHHRS9e/eOv/71r3HiiSfG2LFj44QTToiIqn38q/P444/H119/Hcccc0ymraqPQZ8+fWLkyJExZcqU6Nq1a7Rp0yaOOuqoOOuss+Laa6+NiKo/BlRczqefrzrMY8pKdZ0Hb4jqPofeENV9/r0hqvvcfUOY95etinbNkLtevYFKY+nSpZGXl1eqvU6dOpntVdmq41vbGOTl5VX6sXrvvffijDPOiB49esSgQYMiovoc/5AhQ+Kwww6Lzz//PO67775YuXJlLFu2LCKq/hh8/fXXcfHFF8dFF10UTZs2XW2ftY3BD4+rMo7BrrvuGrvuumvmef/+/eOwww6L7bbbLoYOHRqPPfZYlR6DxYsXx5IlS+LXv/513HDDDRERccghh8SyZcti3LhxMWLEiCp9/KszceLEqFWrVhxxxBGZtuowBu3atYs999wzDj300GjSpEk88sgjMXr06GjRokWceeaZ1WIMqJicTz9fVZ/HlJXqPA/eENV5Dr0hzL83THWfu28I8/6yVdGuGaychyqqbt26mRUNP7TqI09169ZNu6RUrTq+dRmDyjxWc+fOjX79+kVBQUFMnjw5atasGRHV5/i32mqr2GeffeK4446Lhx9+OBYvXhwHHnhgJElS5cfgD3/4QzRu3DjOOuusNfZZ2xj88Lgq4xisTseOHeOggw6Kp59+OlauXFmlx2BVPQMHDizRfvTRR0dExIsvvlilj//HFi9eHH//+9+jd+/e0aRJk0x7VR+Dv/zlL3HqqafGrbfeGqecckoccsghcdttt8WgQYPi/PPPj6+//rrKjwEVl/Pp56vq85iyUN3nwRuiOs+hN4T5d9mrTnP3DWHeX3Yq4jWDcB6qqJYtW2Y+lvNDq9o22WSTtEtK1aqPE61pDBo3bpz5l86WLVvG3LlzI0mSUv0iKu5YLVq0KPbff/9YuHBhPPbYYyXqrA7HvzqHHXZYvPrqq/HBBx9U6TH48MMPY/z48TF48OD4/PPPY/r06TF9+vT47rvvYvny5TF9+vSYP3/+Wsfgx+dMVXnPaN26dSxbtiy+/fbbKj0Gq+pp3rx5ifZmzZpFRMSCBQuq9PH/2IMPPhhLliwp8fHUiLW/H1b2Mbj55puja9eu0apVqxLt/fv3jyVLlsS0adOq/BhQcTmffr6qPI8pC+bBZau6zKE3hPl3+akuc/cNYd5fdiriNYNwHqqoLl26xAcffBCFhYUl2l9++eXM9qps0003jaZNm5b4cplVXnnllRLH36VLl1iyZEm8++67JfpV5LH67rvv4sADD4wPPvggHn744dhmm21KbK/qx78mqz4+tmjRoio9BrNnz47i4uIYPHhwtG/fPvN4+eWX44MPPoj27dvHiBEjonPnzpGbm1tqDJYtWxavv/56qTGoKu8Zn3zySdSpUycaNGhQpcdgxx13jIjvz4cfWnWPw6ZNm1bp4/+xe+65Jxo0aBD9+/cv0V7Vx+CLL76IlStXlmpfvnx5RESsWLGiyo8BFZfz6eeryvOYDWUeXPaqyxx6Q5h/l5/qMnffEOb9ZadCXjMkQJX00ksvJRGR/PGPf8y0fffdd0nHjh2T7t27Z7GysvXqq68mEZHccccdpbb9+te/TurWrZvMnDkz0/bkk08mEZGMGTMm0zZr1qykVq1ayRlnnJFpKy4uTvbYY49k0003TVasWFGux7C+VqxYkfTv3z/Jzc1NHnnkkTX2q6rHnyRJ8sUXX5RqW7ZsWbLDDjskdevWTb755pskSaruGMybNy954IEHSj06deqUtGnTJnnggQeSN998M0mSJOnTp0/SsmXLpLCwMPP7t956axIRyaOPPpppq4zvGV9++WWpttdffz2pVatW0r9//0xbVR2DqVOnJhGRHH300SXaBw4cmOTm5iazZ89OkqTqHv8Pffnll0lubm5y7LHHrnZ7VR6DAw44IKldu3by/vvvl2g/+OCDkxo1alSr84CKx/m0dtVxLrshzIM3THWfQ28I8+8NV93n7hvCvL9sVNRrBuE8VGGHH354kpubm5x33nnJuHHjkl133TXJzc1Nnn322WyXtsFuvPHGZOTIkclpp52WRERyyCGHJCNHjkxGjhyZLFy4MEmSJJk5c2bSpEmTpEOHDskNN9yQjB49OmnUqFGy7bbbJt99912J/Z133nlJRCSnnnpqcssttyT9+vVLIiK55557snF4P+k3v/lNEhHJgQcemNx9992lHqtU1eNPku9Dp7333ju55JJLkltuuSUZOXJkstVWWyURkVx99dWZflV5DFanZ8+eSadOnUq0/ec//0ny8vKSrl27JmPGjEkuvPDCpE6dOsl+++1X6vcr23vGXnvtlfTt2ze59NJLk/HjxydDhgxJ6tWrlxQUFCTvvPNOpl9VHoMTTzwxiYjkiCOOSG666abk8MMPTyIiGTp0aKZPVT7+VW688cYkIpLHHntstdur8hg8++yzSc2aNZNmzZolI0aMSG666aZk//33TyIiOfnkkzP9qvIYULE5n1avOs9lN4R58IYxhy571W3+vSHM3TeMef+Gq6jXDMJ5qMKWLl2anHvuuUmLFi2SvLy8ZOedd17jm1Bl07Zt2yQiVvv49NNPM/3efvvtZL/99kvq1auXbLTRRskxxxyTzJ07t9T+Vq5cmYwePTpp27ZtUrt27aRTp07Jn//85xSPaN317Nlzjcf+4w9EVcXjT5IkmTRpUrLPPvskzZs3T3Jzc5NGjRol++yzT/L3v/+9VN+qOgars7qLgyRJkueeey7Zddddkzp16iRNmzZNzjjjjBKrAVapbO8Z119/fdKtW7ekcePGSW5ubtKyZcvkl7/8ZfLhhx+W6ltVx2DZsmXJJZdckrRt2zapVatW0rFjx+Taa68t1a+qHv8qu+yyS9KsWbOfXKFXlcfg5ZdfTvbff/+kRYsWSa1atZItttgiGTVqVLJ8+fIS/aryGFBxOZ9WrzrPZTeEefCGMYcue9Vt/r0hzN03jHn/hquo1ww5SfKjb+4AAAAAAADKlS+EBQAAAACAlAnnAQAAAAAgZcJ5AAAAAABImXAeAAAAAABSJpwHAAAAAICUCecBAAAAACBlwnkAAAAAAEiZcB4AAAAAAFImnAcAAAAAgJQJ5wEAAAAAIGXCeQAAAAAASJlwHgAAAAAAUiacBwAAAACAlAnnAQAAAAAgZcJ5AAAAAABImXAeAAAAAABSJpwHAAAAAICUCecBAAAAACBlwnkAAAAAAEiZcB4AAAAAAFImnAcAAAAAgJQJ5wEAAAAAIGXCeQAAAAAASJlwHgAAAAAAUiacBwAAAACAlAnnAQAAAAAgZcJ5AAAAAABImXAeAAAAAABSJpwHAAAAAICUCecBAAAAACBlwnkAAAAAAEiZcB4AWKMJEyZETk5O5OTkxCWXXLLW/pdcckmm/4QJE8q9PgAA+LH1ncMCZItwHgCqmS+++CKGDh0a22+/fTRs2DDq1q0bm222WZxwwgnxxhtvZLs8AABS8MNFFat7bLTRRj9rvwsXLoxLLrkkLrnkEos1ANYiN9sFAADp+de//hUDBgyI+fPnl2j/9NNP49NPP4277rorrr322hg8eHCWKgQAoDJbuHBhDB8+PCIievbsGccff3x2CwKowITzAFBNfPbZZ3HwwQfHggULIiJijz32iN/85jfRoEGDuO++++L222+P4uLiGDJkSHTs2DH69u2b5YpLKi4ujmXLlkWdOnWyXQoAQJWy//77xwUXXFCiLTc33cioOs71lixZEvXq1ct2GUAWua0NAFQTV155ZSaY33LLLWPKlClx6KGHRu/eveO2227LrGpKkiR+//vfr3V/9913X3Tq1Cnq1KkTnTt3jvvuu+8n+7/55psxcODAaNmyZdSuXTs23XTTOPnkk+Ozzz4r0e+HH7G+/fbb49JLL422bdtGrVq14qWXXvp5Bw8AwBo1a9Ysdt999xKPXXbZJSIiioqKYptttomcnJyoVatWidsg9uvXLzNvmzRpUhx//PHRvn37zPZnn302s71Xr14Rsfa53rfffhunnXZa7LTTTtG8efOoXbt2FBQURI8ePeK22277Wcd3//33x3bbbRd5eXmxxRZbrHbeOnfu3Bg8eHB06NAh8vLyYqONNopevXrF/fffX6LfM888k6n/x58KWNXerl27TNuP738/duzY2HLLLaNWrVqZOv7617/G7rvvHgUFBVG7du1o0aJF7L777nH++edHkiQ/65iBysHKeQCoJh544IHMz2eddVbk5eWV2P7b3/42c1/Qt956Kz755JM17uv++++Po446KnOx8N///jeOPPLI2G677Vbb/9FHH40BAwZEUVFRpu3zzz+P2267LR555JF44YUXSlzIrTJq1KifrAMAgPKVl5cXd9xxR+y2226xYsWKOPXUU+PFF1+Me++9N/7v//4vIiIOPfTQGDhwYDz++OPrte/VzfW++eabGDt2bIm25cuXx0svvRQvvfRSzJ49Oy6++OJ1fo1777033nvvvczzDz/8MAYOHBjbb799bLnllhHx/S0ed91115g7d26m37Jly+LZZ5+NZ599Ns4///y4/PLL1+vYVufuu+8udbzPPvtsHHHEEVFcXJxp++KLL+KLL76I559/PkaNGpX6pxiA9Fg5DwDVwDfffFNihXqXLl1K9enUqVPUqlUr8/ydd95Z7b5WrlwZZ599diaYP+qoo+KRRx6Js88+O958881S/ZcsWRKDBg2KoqKiyM3NjVGjRsUTTzwRv/vd7yLi+1VKp59++mpf65NPPoljjjkmHnnkkbjrrrti0003XedjBgBg3dx5552lvhD2h6vCu3fvHueee25ERLzyyitx6aWXxpAhQyIiomnTpjFmzJiIiLjwwgtLrDTv0qVLPPfcc/Hcc8/FjTfeWOp1VzfXq1evXowYMSLuu+++eOKJJ+Lpp5+Ov/zlL7H55ptHRMQf//jHWLZs2Tof23vvvRcnnXRSPPzww/GLX/wiIr6/hc6tt96a6XP66adngvlevXrFQw89FNdcc03mFjtXXHFFvPzyy+v8mmvyySefRO/evePBBx/MfAr1H//4RyaYHz16dDz11FPxl7/8Jf7whz9kPrEAVF3+6Q0AqoHCwsISz5s2bVqqT05OTjRp0iRzYbJo0aLV7us///lPzJ49OyIiNtlkk7j77rsjNzc3+vbtG6+88ko8//zzJfo/8cQTMW/evIiI2HfffWPPPfeMiIgDDzww7rvvvpg+fXo8/vjj8dVXX8XGG29c4nd32223+POf//wzjhgAgLI0fPjw+Mc//hHvvPNODBs2LNM+duzYzNxy8803L7HYo6CgIHbfffc17nNNc72uXbvGDTfcENOmTYsFCxbEypUrM9sWL14c77333ho/sflj22+/fSaI33jjjeOpp56KiIiPPvooIiLmz5+fWfGfl5cXkydPjiZNmkRExOzZs+Pqq6+OiIhJkyZF9+7d1+k116Rt27bx8MMPl1gJ/7e//S3z8+abbx7bb799NGnSJI488sgYOXLkBr0eUPEJ5wGgGsjPzy/xfN68ebHFFluUaEuSJL7++uvM84KCgvjqq69K7euHH8Xt0qVLiYuLbt26lQrnP/jgg8zPjz76aDz66KOl9pkkSbz33nulLt4OOOCAnzosAADKwOq+ELZ58+Ylnufl5cWECROie/fumU9QHnHEEXHIIYf87Ndd3Vzvb3/7Wxx66KE/+XsLFy5c59fo2bNn5udVofsP9/Hhhx9mjqdDhw4l+nTr1i3z8w/ntD9Xnz59St2i5phjjolrr702ioqK4vDDD4+I778DYLfddovTTz899tlnnw1+XaDiclsbAKgGGjZsGK1atco8f/3110v1eeedd2L58uWZ59tss816v86GfOz222+/LdX244tCAADK3uq+EHbVbWR+6P333y/xBaXvv/9+ifnj+lrdXO9Pf/pT5ufjjz8+nnjiiXjuuedi3333zbT/8P7sa9OoUaPMzz8Mxtfli1ZXN7f9YdsPV/SvblHLj63ueDt37hz/+c9/YvDgwdG9e/coKCiIL7/8Mh544IHo3bt3vPDCC2vdL1B5CecBoJo4+OCDMz/fdNNNpe7Vec0112R+3nbbbWOzzTZb7X5+2P7666+XuChZ3b04f7hCf9CgQZEkSanHt99+G7179y71u+6xCQBQMcyZMycGDx4cERE1a9aMiIg33ngjRo0aVaJfjRr/i5rWFqKvbq636vaJERE33nhj7LvvvrHrrruWaC9LHTt2zNTx8ccfl/gk6Q/ntqvmtAUFBZm2H36B7GOPPbbW11rd8SZJEp06dYrrr78+XnrppVi4cGFMnjw5Ir4fvwcffHD9DgioVNzWBgCqid/97nfx5z//ORYuXBjvvvtu7LvvvvGb3/wm6tevH5MnT47bb78903f06NFr3M+OO+4Ym266acyePTs+//zzOO644+KXv/xlPPXUU6VuaRPx/X3mmzZtGvPmzYu77rorGjduHPvuu2+sXLkypk+fHs8//3y88cYba/wCWgAAyteXX34Z//73v0u177zzzpGXlxcREb/61a9iwYIFERFx3333xUUXXRTvvPNOjB49Og4++ODo0qVLRJRcqf7WW2/Fgw8+GBtvvHG0adMm2rRps9Za2rZtm7mFzMUXXxy9e/eOu+++u9zmik2aNInevXvHY489FkVFRXHEEUfE2WefHR9//HHcfPPNmX4DBw6MiIj27dtHjRo1ori4OP75z3/GBRdcEA0bNozLL7/8Z73+lVdeGc8880z069cv2rRpE/Xr18/cAz8ioqioaMMOEKjQhPMAUE20bt06/va3v8UhhxwSCxcujH/961/xr3/9q0SfGjVqxFVXXfWT93qvWbNmXHXVVZkLlIkTJ8bEiRMj4vuVR6u+XGuV+vXrx4QJE+KQQw6JoqKiuPbaa+Paa68t0adt27ZlcYgAAPwMa/peoE8//TTatWsXd955Z/zjH/+IiIgjjzwyDjnkkNhkk01it912i+XLl8fxxx8fr776atSqVSsaNmwYO+64Y/znP/+JhQsXxoABAyIiYtiwYXHJJZestZZTTz01pkyZEhGRmTfWqVMns8/ycNNNN8Vuu+0Wc+fOjX/+85/xz3/+s8T2888/P/NlsAUFBXHkkUfGpEmTori4OC677LKIiNh6662jsLBwvV97+fLl8dhjj6125X2NGjXiiCOO+BlHBFQWbmsDANXIXnvtFe+++26cf/750blz56hfv37k5eVFu3btYtCgQfHaa6/F2Wefvdb9HHXUUTFp0qTYeuuto3bt2rHlllvG7bffHsccc8xq+/ft2zdee+21OPbYY6NVq1ZRq1at2HjjjaNLly5xzjnnxP3331/WhwoAQBn4/PPPY8iQIRHx/ar466+/PiIidtlll8xtbt54440YOXJk5ncmTZoUffr0KbGKfl0ddthhMW7cuNh8882jTp06sfPOO8djjz0WnTt33vCDWYPNNtsspk6dGmeeeWa0b98+atWqFfn5+bHnnnvGvffeW2pV/I033hiHH3541K9fPwoKCuK4444rtehlXfXt2zd+9atfRefOnaNRo0ZRs2bNaNy4cey3337x+OOPx2677VYWhwhUUDnJunwDBgAAAAAAUGasnAcAAAAAgJQJ5wEAAAAAIGXCeQAAAAAASJlwHgAAAAAAUiacBwAAAACAlAnnAQAAAAAgZcJ5AAAAAABIWW62CwDKX3FxcXz++efRsGHDyMnJyXY5AADrLUmS+Oabb2KTTTaJGjWsMapszEcBgMquPOajwnmoBj7//PNo3bp1tssAANhgs2bNilatWmW7DNaT+SgAUFWU5XxUOA/VQMOGDSPi+zeP/Pz8LFcDALD+CgsLo3Xr1pl5DZWL+SgAUNmVx3xUOA/VwKqPDufn57sYAgAqNbdEqZzMRwGAqqIs56Nu1ggAAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKcrNdAAAAANVD52GPR428etkuAyq96Zf3y3YJAJQBK+cBAAAAACBlwnkAAAAAAEiZcB4AAAAAAFImnAcAAAAAgJQJ5wEAAAAAIGXCeQAAAAAASJlwHgAAAAAAUiacBwAAAACAlAnnAQAAAAAgZcJ5AAAAAABImXAeAAAAAABSJpwHAAAAAICUCecBAAAAACBlwnkAAAAAAEiZcB4AAAAAAFImnAcAAAAAgJQJ5wEAAAAAIGXCeQAAAAAASJlwHgAAAAAAUiacBwAAAACAlAnnAQAAAAAgZcJ5AAAAAABImXAeAAAAAABSJpwHAAAAAICUCecBAAAAACBlwnkAAAAAAEiZcB4AAAAAAFImnAcAAAAAgJQJ5wEAAAAAIGXCeQAAAAAASJlwHgAAAAAAUiacBwAAAACAlAnnAQAAAAAgZcJ5AAAAAABImXAeAAAAAABSJpwHAAAAAICUCecBAAAAACBlwnkAAAAAAEiZcB4AAAAAAFImnAcAAAAAgJQJ5wEAAAAAIGXCeQAAAAAASJlwHgAAoIraf//9o1GjRvHFF1+U2rZo0aJo2bJldO/ePYqLi7NQHQBA9SacBwAAqKJuvvnmWLZsWZx99tmltl1wwQXx1Vdfxfjx46NGDZeGAABpMwMDAACootq3bx/Dhg2LSZMmxRNPPJFpf/XVV2Ps2LFxzjnnxPbbb5/FCgEAqi/hPAAAQBV2zjnnxHbbbRenn356fPfdd7Fy5cr49a9/HW3bto1hw4bFe++9F4cddlg0btw46tSpEzvttFM89NBDJfaxfPnyGD58eGy++eZRp06daNKkSey+++4xZcqULB0VAEDll5vtAgAAACg/ubm5MX78+Nh1111j5MiR0axZs5g6dWo89thj8emnn8Zuu+0Wm266afz+97+P+vXrx3333RcHH3xw/PWvf40BAwZERMQll1wSl112WZx88snRrVu3KCwsjNdeey2mTp0a++67b5aPEACgcspJkiTJdhFA+SosLIyCgoJYtGhR5OfnZ7scAID1Zj6z4c4666wYN25c5OXlxYEHHhgTJ06MffbZJ7788st49dVXIy8vLyIikiSJ3XffPebNmxcffPBBRER06dIlWrVqFQ8//PA6vVZRUVEUFRVlnhcWFkbr1q2j9ZD7okZevbI/OKhmpl/eL9slAFQ75TEftXIeqpHOwx53MQQAlCkBUeUxatSomDx5cixZsiSuvfbamD9/fvzzn/+MESNGxDfffBPffPNNpm/v3r1j2LBhMXv27Nh0001jo402iv/+97/x4Ycfxuabb77W17rsssti+PDh5Xk4AACVnnvOAwAAVAP5+fmx5ZZbRuvWraN58+bx0UcfRZIkcdFFF0XTpk1LPIYNGxYREV9++WVERIwYMSIWLlwYW2yxRWy77bZx3nnnxZtvvrnG1xo6dGgsWrQo85g1a1YqxwgAUJlYOQ8AAFANFRcXR0TEueeeG717915tn44dO0ZExJ577hkff/xx/P3vf48nnngibr311rj22mtj7NixcfLJJ5f6vby8vMxtcgAAWD3hPAAAQDW02WabRURErVq1Yp999llr/8aNG8cJJ5wQJ5xwQixevDj23HPPuOSSS1YbzgMAsHZuawMAAFANNWvWLHr16hXjxo2LOXPmlNo+b968zM9ff/11iW0NGjSIjh07lvjSVwAA1o+V8wAAANXUTTfdFLvvvntsu+22ccopp8Rmm20WX3zxRbz44ovx2WefxRtvvBEREdtss0306tUrdtxxx2jcuHG89tprMXny5DjzzDOzfAQAAJWXcB4AAKCa2mabbeK1116L4cOHx4QJE+Lrr7+OZs2aRdeuXePiiy/O9Bs8eHA89NBD8cQTT0RRUVG0bds2Lr300jjvvPOyWD0AQOUmnAcAAKgmnnnmmVJtm222Wdx5550/+XsXXnhhXHjhheVUFQBA9eSe8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkTDgPAAAAAAApE84DAAAAAEDKhPMAAAAAAJAy4TwAAAAAAKRMOA8AAAAAACkTzgMAAAAAQMqE8wAAAAAAkDLhPAAAAAAApEw4DwAAAAAAKRPOAwAAAABAyoTzAAAAAACQMuE8AAAAAACkLDfbBQAAAFA9vD28d+Tn52e7DACACsHKeQAAAAAASJlwHgAAAAAAUiacBwAAAACAlAnnAQAAAAAgZcJ5AAAAAABImXAeAAAAAABSJpwHAAAAAICUCecBAAAAACBlwnkAAAAAAEiZcB4AAKACWbp0aSxZsiTzfMaMGXHdddfFE088kcWqAAAoa8J5AACACuSggw6Ku+66KyIiFi5cGN27d4+rr746DjrooBgzZkyWqwMAoKwI5wEAACqQqVOnxh577BEREZMnT47mzZvHjBkz4q677oobbrghy9UBAFBWhPMAAAAVyJIlS6Jhw4YREfHEE0/EIYccEjVq1IhddtklZsyYkeXqAAAoK8J5AACACqRjx47x4IMPxqxZs+Lxxx+P/fbbLyIivvzyy8jPz89ydQAAlBXhPAAAQAVy8cUXx7nnnhvt2rWL7t27R48ePSLi+1X0Xbt2zXJ1AACUldxsFwAAAMD/HHbYYbH77rvHnDlzYvvtt8+0/+IXv4gBAwZksTIAAMqScB4AAKCCWL58edStWzdef/31Uqvku3XrlqWqAAAoD25rAwAAUEHUqlUr2rRpEytXrsx2KQAAlDPhPAAAQAVy4YUXxgUXXBDz58/PdikAAJQjt7UBAACoQP70pz/FRx99FJtsskm0bds26tevX2L71KlTs1QZAABlSTgPAABQgRx88MHZLgEAgBQI5wEAACqQYcOGZbsEAABS4J7zAAAAAACQMivnAQAAKpAaNWpETk7OGrevXLkyxWoAACgvwnkAAIAK5IEHHijxfPny5TFt2rS48847Y/jw4VmqCgCAsiacBwAAqEAOOuigUm2HHXZYdOrUKe6999446aSTslAVAABlzT3nAQAAKoFddtklnnrqqWyXAQBAGRHOAwAAVHBLly6NG264ITbddNNslwIAQBlxWxsAAIAKpFGjRiW+EDZJkvjmm2+iXr168ec//zmLlQEAUJaE8wAAABXIddddV+J5jRo1omnTptG9e/do1KhRdooCAKDMCecBAAAqkEGDBmW7BAAAUiCchzK2fPny2GqrreLhhx+OrbfeOtvlAABQCS1cuDBuu+22ePfddyMiolOnTnHiiSdGQUFBlisDAKCs+EJYKGO1atWK7777LttlAABQSb322mvRoUOHuPbaa2P+/Pkxf/78uOaaa6JDhw4xderUbJcHAEAZEc5DOTjjjDPiiiuuiBUrVmS7FAAAKpmzzz47+vfvH9OnT4+//e1v8be//S0+/fTTOOCAA2LIkCHZLg8AgDLitjZQDl599dV46qmn4oknnohtt9026tevX2L73/72tyxVBgBARffaa6/FLbfcErm5/7tcy83Njd/97nex0047ZbEyAADKknAeysFGG20Uhx56aLbLAACgEsrPz4+ZM2fGVlttVaJ91qxZ0bBhwyxVBQBAWRPOQzm44447sl0CAACV1JFHHhknnXRSXHXVVbHrrrtGRMTzzz8f5513XgwcODDL1QEAUFaE81BOVqxYEc8880x8/PHHcfTRR0fDhg3j888/j/z8/GjQoEG2ywMAoIK66qqrIicnJ4477rjMdxjVqlUrTjvttLj88suzXB0AAGVFOA/lYMaMGdGnT5+YOXNmFBUVxb777hsNGzaMK664IoqKimLs2LHZLhEAgAqqdu3acf3118dll10WH3/8cUREdOjQIerVq5flygAAKEs1sl0AVEW/+c1vYqeddooFCxZE3bp1M+0DBgyIp556KouVAQBQWdSrVy+23Xbb2HbbbQXzAABVkJXzUA6ee+65eOGFF6J27dol2tu1axezZ8/OUlUAAFQG3377bVx++eXx1FNPxZdffhnFxcUltn/yySdZqgwAgLIknIdyUFxcHCtXrizV/tlnn0XDhg2zUBEAAJXFySefHM8++2wce+yx0bJly8jJycl2SQAAlAPhPJSD/fbbL6677roYP358RETk5OTE4sWLY9iwYdG3b9913s/+++8fL730Urz33nvRvHnzEtsWLVoUW221VbRp0yZefPHFqFHDXaoAAKqCRx99NB555JHYbbfdsl0KAADlSJoH5eDqq6+O559/PrbZZpv47rvv4uijj87c0uaKK65Y5/3cfPPNsWzZsjj77LNLbbvgggviq6++ivHjxwvmAQCqkEaNGkXjxo2zXQYAAOVMogfloFWrVvHGG2/EBRdcEGeffXZ07do1Lr/88pg2bVo0a9ZsnffTvn37GDZsWEyaNCmeeOKJTPurr74aY8eOjXPOOSe233778jgEAACyZOTIkXHxxRfHkiVLsl0KAADlKCdJkiTbRQBrtmLFithxxx3j22+/jbfffjtq1aoV3bp1iwULFsTbb78d9erVW+s+CgsLo6CgIFoPuS9q5K29PwDAupp+eb9UXmfVfGbRokWRn5+fymumqWvXriXuLf/RRx9FkiTRrl27qFWrVom+U6dOTbu8DVbV/34AQNVXHvMZ95yHMvLQQw+tc9/+/fuvc9/c3NwYP3587LrrrjFy5Mho1qxZTJ06NR577LF1CuYBAKj4Dj744GyXAABAyoTzUEZ+fEGVk5MTP/5gyqrVUCtXrlyvfXfv3j1OP/30+OMf/xh5eXkxcODA6N279xr7FxUVRVFRUeZ5YWHher0eAADpGjZsWLZLAAAgZe45D2WkuLg483jiiSeiS5cu8eijj8bChQtj4cKF8eijj8YOO+wQjz322M/a/6hRo6JJkyZRo0aNuPbaa3+y72WXXRYFBQWZR+vWrX/WawIAAAAA5cPKeSgHQ4YMibFjx8buu++eaevdu3fUq1cvTj311Hj33XfXe5/5+fmx5ZZbxldffRXNmzf/yb5Dhw6Nc845J/O8sLBQQA8AAAAAFYhwHsrBxx9/HBtttFGp9oKCgpg+fXq5v35eXl7k5eWV++sAAAAAAD+P29pAOdh5553jnHPOiS+++CLT9sUXX8R5550X3bp1y2JlAAAAAEBFIJyHcnD77bfHnDlzok2bNtGxY8fo2LFjtGnTJmbPnh233XZbtssDAAAAALLMbW2gHHTs2DHefPPNmDJlSrz33nsREbH11lvHPvvsEzk5OVmuDgCAiu6zzz6Lhx56KGbOnBnLli0rse2aa67JUlUAAJQl4TyUk5ycnNhvv/1iv/32y3YpAABUIk899VT0798/Nttss3jvvfeic+fOMX369EiSJHbYYYdslwcAQBkRzkMZueGGG9a57+DBg3/WazzzzDM/6/cAAKg8hg4dGueee24MHz48GjZsGH/961+jWbNmccwxx0SfPn2yXR4AAGVEOA9l5Nprr12nfjk5OT87nAcAoOp79913Y9KkSRERkZubG0uXLo0GDRrEiBEj4qCDDorTTjstyxUCAFAWhPNQRj799NNSbfPmzYucnJzYeOONs1ARAACVUf369TP3mW/ZsmV8/PHH0alTp4iI+Oqrr7JZGgAAZahGtguAqmbhwoVxxhlnxMYbbxwtWrSI5s2bx8YbbxxnnnlmLFq0KNvlAQBQwe2yyy7x73//OyIi+vbtG7/97W9j1KhRceKJJ8Yuu+yS5eoAACgrVs5DGZo/f3706NEjZs+eHcccc0xsvfXWERHxzjvvxIQJE+Kpp56KF154IRo1apTlSgEAqKiuueaaWLx4cUREDB8+PBYvXhz33ntvbL755nHNNddkuToAAMqKcB7K0IgRI6J27drx8ccfR/PmzUtt22+//WLEiBHrfH96AACql5UrV8Znn30W2223XUR8f4ubsWPHZrkqAADKg9vaQBl68MEH46qrrioVzEdEtGjRIq688sp44IEHslAZAACVQc2aNWO//faLBQsWZLsUAADKmXAeytCcOXMyX9a1Op07d465c+emWBEAAJVN586d45NPPsl2GQAAlDPhPJShjTfeOKZPn77G7Z9++mk0btw4vYIAAKh0Lr300jj33HPj4Ycfjjlz5kRhYWGJBwAAVYN7zkMZ6t27d1x44YUxZcqUqF27doltRUVFcdFFF0WfPn2yVB0AAJVB3759IyKif//+kZOTk2lPkiRycnJi5cqV2SoNAIAyJJyHMjRixIjYaaedYvPNN48zzjgjttpqq0iSJN599924+eabo6ioKO6+++5slwkAQAX29NNPZ7sEAABSIJyHMtSqVat48cUX4/TTT4+hQ4dGkiQREZGTkxP77rtv/OlPf4rWrVtnuUoAACqy9u3bR+vWrUusmo/4fuX8rFmzslQVAABlTTgPZax9+/bx6KOPxoIFC+LDDz+MiIiOHTu61zwAAOukffv2MWfOnGjWrFmJ9vnz50f79u3d1gYAoIoQzkM5adSoUXTr1i3bZQAAUMmsurf8jy1evDjq1KmThYoAACgPwnkAAIAK4JxzzomI72+JeNFFF0W9evUy21auXBkvv/xydOnSJUvVAQBQ1oTzAAAAFcC0adMi4vuV82+99VbUrl07s6127dqx/fbbx7nnnput8gAAKGPCeQAAgArg6aefjoiIE044Ia6//vrIz8/PckUAAJSnGtkuAAAAgP+58sor1xjMv/XWWylXAwBAeRHOAwAAVCDbbrttPPLII6Xar7rqqujWrVsWKgIAoDwI5wEAACqQc845Jw499NA47bTTYunSpTF79uz4xS9+EVdeeWVMnDgx2+UBAFBGhPMAAAAVyO9+97t48cUX47nnnovtttsutttuu8jLy4s333wzBgwYkO3yAAAoI8J5AACACqZjx47RuXPnmD59ehQWFsaRRx4ZLVq0yHZZAACUIeE8AABABfL888/HdtttFx9++GG8+eabMWbMmDjrrLPiyCOPjAULFmS7PAAAyohwHgAAoALZe++948gjj4yXXnoptt566zj55JNj2rRpMXPmzNh2222zXR4AAGUkN9sFAAAA8D9PPPFE9OzZs0Rbhw4d4vnnn49Ro0ZlqSoAAMqalfMAAAAVyI+D+VVq1KgRF110UcrVAABQXoTzAAAAFUDfvn1j0aJFmeeXX355LFy4MPP866+/jm222SYLlQEAUB6E8wAAABXA448/HkVFRZnno0ePjvnz52eer1ixIt5///1slAYAQDkQzgMAAFQASZL85HMAAKoW4TwAAAAAAKRMOA8AAFAB5OTkRE5OTqk2AACqptxsFwAA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/vzzzyz1cnuvABRoBgAAuNSkSZOMpGxfAQEBZufOncYYY/r06ZNjvZiYGHt799xzT471RowYYa/3008/mcKFC2dbLzAw0GzevNled+zYsTm22aBBA3u93MbYs2dPe3m5cuUc6nbv3t1ER0c7lM+fPz9L3/Xo0SPH4z388MNZ6kZGRtq3lS1bNsf4vvnmmxzblGQSEhL+/YcOAADcVm7GWn379s2xTvHixc3ff/9tjDGmSZMmOdbr2bOnMSbruOmbb74xxhiza9cu4+/vn+O+e/bsMQkJCTlub9KkiTHGmFatWuVYp0qVKiYtLc1+3vHx8SYsLOyqsV5tDLVgwQJjTNYx2WWZmZmmS5cuOe5buXJlc+LECXv9K/stu3HdlePT3EhKSjJlypS5al8ZY8zmzZtNUFBQtvVsNpt544037HWvHFNe7p+cPk9jjJk/f77x8PDItu1KlSplOf/c3j8YY8wff/yR7Zi/Ro0a2cZ3Zd9eOe596aWXHD5LY4z54osvjK+vb7axlChRwvzxxx/2urm9VwAKMmbOAwDgYnXq1NGsWbP02Wef6ZtvvtGaNWs0ZcoUSVJqaqqmT58uSfr0008lSZGRkVq2bJlWr16tt956Sz169FBoaKgk6fTp0/rmm28kSbVq1dJnn32mlStXas6cOXrwwQdVqFAhSZIxRj179tSpU6ckSc8++6xWr16tKVOmyNPTU2fOnFHv3r3t65NePnbhwoX13nvvae3atXr33XfVr18/lSxZ0n4uuYnxnw4fPqx58+bpzTfflIfHpaHIokWLlJaWpvfff1+jR4+21507d67972XLlundd9+VJFWqVElLlizR//73P911112SpKVLl9pncf1TWlqa3nvvPb3xxhvy8fGRJL3//vtKTk5WrVq1FBcXl2V91A8//FBxcXGKi4vLcr4AAKBgye1Yq2XLlpo7d67+97//ad26dVq1apWeffZZSdLff/+tN998U5I0a9YszZw5095+mzZt7GOOESNG5BjHmjVrlJaWJkkaOHCgvvrqKy1btkzjx4/XHXfcIZvNppIlSyouLk5t2rSx7zdz5kzFxcVp1qxZki4tc/P2229rxYoVWrdunVasWKEePXpIkn777Td9/PHHki6NHXv06GH/pWH16tW1aNEirVixQqNGjVKRIkUkXZr53bt3b/vxhg8fbj+ftm3b5ng+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7tw53Xvvvdq9e7c+//xzVa1aNcv2W265RcWKFdOPP/7osO8PP/yQpU9r1qyp1NRU/fbbb1nqFbT+P3jwoDIzMzVgwABFR0fbX5s3b9bu3bsVHR2tsWPHqnr16vLy8nLo2/Pnz2vbtm0OfVvQv9u33367pEv9e6XLawgWK1aMPr1Of//9tzIyMhzKL1y4IEm6ePEifXsD5MX11Jk2C4LNmzerY8eOuuOOO/TBBx/Iy8vxB7OX++Sfffbjjz8qMzPTvt3Dw0O33nprtn27efNmlS1bVkFBQTf8HOD+uAbmL4yF3Q/3NwXD5aVKkpOT+UzdCPfKsDMA8qXvv//eSDL//e9/7WXnzp0z5cuXN3Xr1rUwspvTxYsXTYcOHYyXl5dZsWJFjvX69etn/P39TVJSkr1s7dq1RpKZPXu2vezAgQPG29vbPP300/ayzMxM06hRI3PLLbeYixcv5s2J3GSOHj1qli9f7vCqVq2aKVOmjFm+fLnZvn27McaY1q1bm5IlS5qUlBT7/m+++aaRZFauXGkv47ttzNatW40k061btyzlXbt2NV5eXubgwYPGGPr0erRv3974+PiY33//PUv5/fffbzw8POhbJ23ZssVIMgsWLHDYlhfX09y2mR9crW937txpihQpYqpVq2ZOnDiRYxupqakmLCzMtG/fPkv5I488YgICAszx48ftZZMnTzaSzJYtW+xlu3btMp6enub555//9yeEfKmgXwPdlauv3cgb3N/kP3///bdD2fnz503t2rWNv7+/OX36tDGGz9RdcK+My0jOA/nYQw89ZLy8vMzQoUPN3LlzTf369Y2Xl5dZv3691aHddAYOHGgkmXvvvdcsWrTI4XVZUlKSKVKkiClXrpyZOXOmmThxogkNDTW33nqrOXfuXJY2hw4daiSZJ554wsyfP9+0a9fOSDKLFy929enddJo0aWKqVauWpeynn34yvr6+platWmb27NlmxIgRxs/Pz7Rs2dJhf77bxvTp08dIMp07dzavv/66eeihh4wkM2zYMHsd+tR569evN56eniY8PNyMHTvWvP7666ZNmzZGknnsscfs9ejbq5s1a5YZN26cefLJJ40k88ADD5hx48aZcePGmVOnThlj8uZ66kyb7upafZuSkmIiIiKMh4eHmTx5ssN/z7777rss7b3++utGkunUqZOZP3++6dGjh5FkJkyYkKVeSkqKKVeunAkPDzdTp04106dPNxEREaZUqVLmyJEjruwCuJmCeA10V1Zdu5E3uL/Jf+6//35zzz33mNGjR5v58+ebcePGmcqVKxtJ5pVXXrHX4zN1b9wrFzwk54F8LC0tzQwZMsSUKFHC+Pr6mjvvvNOsWrXK6rBuSk2aNDGScnxd6ZdffjEtW7Y0AQEBpnDhwiYmJsYcPnzYoc2MjAwzceJEExkZaXx8fEy1atXMe++956pTuqllN+Awxpi4uDhTv3594+fnZ4oVK2aefvrpLLMDLuO7fWmWzOjRo01kZKTx9vY25cuXN9OnT3eoR586b/PmzaZNmzamRIkSxtvb21SsWNFMmDDBXLhwIUs9+jZnkZGROV5PExIS7PXy4nqa2zbd1bX6NiEh4ar/PevZs6dDm/PmzTOVKlUyPj4+ply5cmb69OkmMzPTod6BAwdMp06dTHBwsAkMDDTt27c3e/bsccFZw50VxGugu7Ly2o0bj/ub/GfJkiWmefPmpnjx4sbLy8uEhoaa5s2bm08//dShLp+p++JeueCxGfOPJz8AAAAAAAAAAIA8xQNhAQAAAAAAAABwMZLzAAAAAAAAAAC4GMl5AAAAAAAAAABcjOQ8AAAAAAAAAAAuRnIeAAAAAAAAAAAXIzkPAAAAAAAAAICLkZwHAAAAAAAAAMDFSM4DAAAAAAAAAOBiJOcBAAAAAAAAAHAxkvMAAAAAAAAAALgYyXkAAAAAAAAAAFyM5DwAAAAAAAAAAC5Gch4AAAAAAAAAABf7fwDOkGLkkCjYAAAAAElFTkSuQmCC",
      "text/plain": [
       "<Figure size 1600x4200 with 14 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "graficos_eda_categoricos(df.select_dtypes('O'))"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "8fa6fea3",
   "metadata": {
    "papermill": {
     "duration": 0.017118,
     "end_time": "2023-10-05T21:57:14.580530",
     "exception": false,
     "start_time": "2023-10-05T21:57:14.563412",
     "status": "completed"
    },
    "tags": []
   },
   "source": [
    "### Cloncusiones\n",
    "* mayor edad solo tiene un valor --> elimarla\n",
    "* sobre las imputaciones pendientes de variable categoricas:\n",
    "    * educacion: imputar por \"Universitaria\"\n",
    "    * satisfacion trabajo: imputar por \"Alta\"\n",
    "    * implicacion: imputar por \"ALta\""
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 9,
   "id": "995312f3",
   "metadata": {
    "execution": {
     "iopub.execute_input": "2023-10-05T21:57:14.617639Z",
     "iopub.status.busy": "2023-10-05T21:57:14.616857Z",
     "iopub.status.idle": "2023-10-05T21:57:16.265970Z",
     "shell.execute_reply": "2023-10-05T21:57:16.264263Z"
    },
    "papermill": {
     "duration": 1.669626,
     "end_time": "2023-10-05T21:57:16.267652",
     "exception": true,
     "start_time": "2023-10-05T21:57:14.598026",
     "status": "failed"
    },
    "tags": []
   },
   "outputs": [
    {
     "ename": "KeyError",
     "evalue": "\"['mayor_edad'] not found in axis\"",
     "output_type": "error",
     "traceback": [
      "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[0;31mKeyError\u001b[0m                                  Traceback (most recent call last)",
      "Cell \u001b[0;32mIn[9], line 1\u001b[0m\n\u001b[0;32m----> 1\u001b[0m \u001b[43mdf\u001b[49m\u001b[38;5;241;43m.\u001b[39;49m\u001b[43mdrop\u001b[49m\u001b[43m(\u001b[49m\u001b[43mcolumns\u001b[49m\u001b[43m \u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43m \u001b[49m\u001b[38;5;124;43m'\u001b[39;49m\u001b[38;5;124;43mmayor_edad\u001b[39;49m\u001b[38;5;124;43m'\u001b[39;49m\u001b[43m,\u001b[49m\u001b[43m \u001b[49m\u001b[43minplace\u001b[49m\u001b[43m \u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43m \u001b[49m\u001b[38;5;28;43;01mTrue\u001b[39;49;00m\u001b[43m)\u001b[49m\n\u001b[1;32m      2\u001b[0m df[\u001b[38;5;124m'\u001b[39m\u001b[38;5;124meducacion\u001b[39m\u001b[38;5;124m'\u001b[39m] \u001b[38;5;241m=\u001b[39m df[\u001b[38;5;124m'\u001b[39m\u001b[38;5;124meducacion\u001b[39m\u001b[38;5;124m'\u001b[39m]\u001b[38;5;241m.\u001b[39mfillna(\u001b[38;5;124m'\u001b[39m\u001b[38;5;124mUniversitaria\u001b[39m\u001b[38;5;124m'\u001b[39m)\n\u001b[1;32m      3\u001b[0m df[\u001b[38;5;124m'\u001b[39m\u001b[38;5;124msatisfaccion_trabajo\u001b[39m\u001b[38;5;124m'\u001b[39m] \u001b[38;5;241m=\u001b[39m df[\u001b[38;5;124m'\u001b[39m\u001b[38;5;124msatisfaccion_trabajo\u001b[39m\u001b[38;5;124m'\u001b[39m]\u001b[38;5;241m.\u001b[39mfillna(\u001b[38;5;124m'\u001b[39m\u001b[38;5;124mAlta\u001b[39m\u001b[38;5;124m'\u001b[39m)\n",
      "File \u001b[0;32m/opt/conda/lib/python3.10/site-packages/pandas/core/frame.py:5258\u001b[0m, in \u001b[0;36mDataFrame.drop\u001b[0;34m(self, labels, axis, index, columns, level, inplace, errors)\u001b[0m\n\u001b[1;32m   5110\u001b[0m \u001b[38;5;28;01mdef\u001b[39;00m \u001b[38;5;21mdrop\u001b[39m(\n\u001b[1;32m   5111\u001b[0m     \u001b[38;5;28mself\u001b[39m,\n\u001b[1;32m   5112\u001b[0m     labels: IndexLabel \u001b[38;5;241m=\u001b[39m \u001b[38;5;28;01mNone\u001b[39;00m,\n\u001b[0;32m   (...)\u001b[0m\n\u001b[1;32m   5119\u001b[0m     errors: IgnoreRaise \u001b[38;5;241m=\u001b[39m \u001b[38;5;124m\"\u001b[39m\u001b[38;5;124mraise\u001b[39m\u001b[38;5;124m\"\u001b[39m,\n\u001b[1;32m   5120\u001b[0m ) \u001b[38;5;241m-\u001b[39m\u001b[38;5;241m>\u001b[39m DataFrame \u001b[38;5;241m|\u001b[39m \u001b[38;5;28;01mNone\u001b[39;00m:\n\u001b[1;32m   5121\u001b[0m \u001b[38;5;250m    \u001b[39m\u001b[38;5;124;03m\"\"\"\u001b[39;00m\n\u001b[1;32m   5122\u001b[0m \u001b[38;5;124;03m    Drop specified labels from rows or columns.\u001b[39;00m\n\u001b[1;32m   5123\u001b[0m \n\u001b[0;32m   (...)\u001b[0m\n\u001b[1;32m   5256\u001b[0m \u001b[38;5;124;03m            weight  1.0     0.8\u001b[39;00m\n\u001b[1;32m   5257\u001b[0m \u001b[38;5;124;03m    \"\"\"\u001b[39;00m\n\u001b[0;32m-> 5258\u001b[0m     \u001b[38;5;28;01mreturn\u001b[39;00m \u001b[38;5;28;43msuper\u001b[39;49m\u001b[43m(\u001b[49m\u001b[43m)\u001b[49m\u001b[38;5;241;43m.\u001b[39;49m\u001b[43mdrop\u001b[49m\u001b[43m(\u001b[49m\n\u001b[1;32m   5259\u001b[0m \u001b[43m        \u001b[49m\u001b[43mlabels\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43mlabels\u001b[49m\u001b[43m,\u001b[49m\n\u001b[1;32m   5260\u001b[0m \u001b[43m        \u001b[49m\u001b[43maxis\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43maxis\u001b[49m\u001b[43m,\u001b[49m\n\u001b[1;32m   5261\u001b[0m \u001b[43m        \u001b[49m\u001b[43mindex\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43mindex\u001b[49m\u001b[43m,\u001b[49m\n\u001b[1;32m   5262\u001b[0m \u001b[43m        \u001b[49m\u001b[43mcolumns\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43mcolumns\u001b[49m\u001b[43m,\u001b[49m\n\u001b[1;32m   5263\u001b[0m \u001b[43m        \u001b[49m\u001b[43mlevel\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43mlevel\u001b[49m\u001b[43m,\u001b[49m\n\u001b[1;32m   5264\u001b[0m \u001b[43m        \u001b[49m\u001b[43minplace\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43minplace\u001b[49m\u001b[43m,\u001b[49m\n\u001b[1;32m   5265\u001b[0m \u001b[43m        \u001b[49m\u001b[43merrors\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43merrors\u001b[49m\u001b[43m,\u001b[49m\n\u001b[1;32m   5266\u001b[0m \u001b[43m    \u001b[49m\u001b[43m)\u001b[49m\n",
      "File \u001b[0;32m/opt/conda/lib/python3.10/site-packages/pandas/core/generic.py:4549\u001b[0m, in \u001b[0;36mNDFrame.drop\u001b[0;34m(self, labels, axis, index, columns, level, inplace, errors)\u001b[0m\n\u001b[1;32m   4547\u001b[0m \u001b[38;5;28;01mfor\u001b[39;00m axis, labels \u001b[38;5;129;01min\u001b[39;00m axes\u001b[38;5;241m.\u001b[39mitems():\n\u001b[1;32m   4548\u001b[0m     \u001b[38;5;28;01mif\u001b[39;00m labels \u001b[38;5;129;01mis\u001b[39;00m \u001b[38;5;129;01mnot\u001b[39;00m \u001b[38;5;28;01mNone\u001b[39;00m:\n\u001b[0;32m-> 4549\u001b[0m         obj \u001b[38;5;241m=\u001b[39m \u001b[43mobj\u001b[49m\u001b[38;5;241;43m.\u001b[39;49m\u001b[43m_drop_axis\u001b[49m\u001b[43m(\u001b[49m\u001b[43mlabels\u001b[49m\u001b[43m,\u001b[49m\u001b[43m \u001b[49m\u001b[43maxis\u001b[49m\u001b[43m,\u001b[49m\u001b[43m \u001b[49m\u001b[43mlevel\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43mlevel\u001b[49m\u001b[43m,\u001b[49m\u001b[43m \u001b[49m\u001b[43merrors\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43merrors\u001b[49m\u001b[43m)\u001b[49m\n\u001b[1;32m   4551\u001b[0m \u001b[38;5;28;01mif\u001b[39;00m inplace:\n\u001b[1;32m   4552\u001b[0m     \u001b[38;5;28mself\u001b[39m\u001b[38;5;241m.\u001b[39m_update_inplace(obj)\n",
      "File \u001b[0;32m/opt/conda/lib/python3.10/site-packages/pandas/core/generic.py:4591\u001b[0m, in \u001b[0;36mNDFrame._drop_axis\u001b[0;34m(self, labels, axis, level, errors, only_slice)\u001b[0m\n\u001b[1;32m   4589\u001b[0m         new_axis \u001b[38;5;241m=\u001b[39m axis\u001b[38;5;241m.\u001b[39mdrop(labels, level\u001b[38;5;241m=\u001b[39mlevel, errors\u001b[38;5;241m=\u001b[39merrors)\n\u001b[1;32m   4590\u001b[0m     \u001b[38;5;28;01melse\u001b[39;00m:\n\u001b[0;32m-> 4591\u001b[0m         new_axis \u001b[38;5;241m=\u001b[39m \u001b[43maxis\u001b[49m\u001b[38;5;241;43m.\u001b[39;49m\u001b[43mdrop\u001b[49m\u001b[43m(\u001b[49m\u001b[43mlabels\u001b[49m\u001b[43m,\u001b[49m\u001b[43m \u001b[49m\u001b[43merrors\u001b[49m\u001b[38;5;241;43m=\u001b[39;49m\u001b[43merrors\u001b[49m\u001b[43m)\u001b[49m\n\u001b[1;32m   4592\u001b[0m     indexer \u001b[38;5;241m=\u001b[39m axis\u001b[38;5;241m.\u001b[39mget_indexer(new_axis)\n\u001b[1;32m   4594\u001b[0m \u001b[38;5;66;03m# Case for non-unique axis\u001b[39;00m\n\u001b[1;32m   4595\u001b[0m \u001b[38;5;28;01melse\u001b[39;00m:\n",
      "File \u001b[0;32m/opt/conda/lib/python3.10/site-packages/pandas/core/indexes/base.py:6699\u001b[0m, in \u001b[0;36mIndex.drop\u001b[0;34m(self, labels, errors)\u001b[0m\n\u001b[1;32m   6697\u001b[0m \u001b[38;5;28;01mif\u001b[39;00m mask\u001b[38;5;241m.\u001b[39many():\n\u001b[1;32m   6698\u001b[0m     \u001b[38;5;28;01mif\u001b[39;00m errors \u001b[38;5;241m!=\u001b[39m \u001b[38;5;124m\"\u001b[39m\u001b[38;5;124mignore\u001b[39m\u001b[38;5;124m\"\u001b[39m:\n\u001b[0;32m-> 6699\u001b[0m         \u001b[38;5;28;01mraise\u001b[39;00m \u001b[38;5;167;01mKeyError\u001b[39;00m(\u001b[38;5;124mf\u001b[39m\u001b[38;5;124m\"\u001b[39m\u001b[38;5;132;01m{\u001b[39;00m\u001b[38;5;28mlist\u001b[39m(labels[mask])\u001b[38;5;132;01m}\u001b[39;00m\u001b[38;5;124m not found in axis\u001b[39m\u001b[38;5;124m\"\u001b[39m)\n\u001b[1;32m   6700\u001b[0m     indexer \u001b[38;5;241m=\u001b[39m indexer[\u001b[38;5;241m~\u001b[39mmask]\n\u001b[1;32m   6701\u001b[0m \u001b[38;5;28;01mreturn\u001b[39;00m \u001b[38;5;28mself\u001b[39m\u001b[38;5;241m.\u001b[39mdelete(indexer)\n",
      "\u001b[0;31mKeyError\u001b[0m: \"['mayor_edad'] not found in axis\""
     ]
    }
   ],
   "source": [
    "df.drop(columns = 'mayor_edad', inplace = True)\n",
    "df['educacion'] = df['educacion'].fillna('Universitaria')\n",
    "df['satisfaccion_trabajo'] = df['satisfaccion_trabajo'].fillna('Alta')\n",
    "df['implicacion'] = df['implicacion'].fillna('Alta')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "c54e3dd8",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.536301Z",
     "iopub.status.idle": "2023-10-05T21:45:43.536639Z",
     "shell.execute_reply": "2023-10-05T21:45:43.536493Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.536478Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df.info()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "4c2c46dc",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### EDA VARIABLES NUMERICAS\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "c7955867",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.539512Z",
     "iopub.status.idle": "2023-10-05T21:45:43.540147Z",
     "shell.execute_reply": "2023-10-05T21:45:43.539885Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.539857Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "def estadisticos_cont(num):\n",
    "    #calculamos describe\n",
    "    estadisticos = num.describe().T\n",
    "    #anadimos la mediana\n",
    "    estadisticos['median'] = num.median()\n",
    "    #reordenamos pra que la mediana este al lado de la media\n",
    "    estadisticos= estadisticos.iloc[:,[0,1,8,2,3,4,5,6,7]]\n",
    "    #lo devolvemos\n",
    "    return(estadisticos)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "a145b65c",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.541474Z",
     "iopub.status.idle": "2023-10-05T21:45:43.542030Z",
     "shell.execute_reply": "2023-10-05T21:45:43.541774Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.541750Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "estadisticos_cont(df.select_dtypes('number'))"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "94f68a06",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### Conclusiones\n",
    "* Empleados solo tiene un valor --> elimarlo\n",
    "* sexo tiene 3 valores --> eliminarlo\n",
    "* horas quincena solo tiene un valor --> eliminarlo"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "5cce5bb3",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.545577Z",
     "iopub.status.idle": "2023-10-05T21:45:43.547041Z",
     "shell.execute_reply": "2023-10-05T21:45:43.546782Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.546746Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df.drop(columns=['empleados','sexo','horas_quincena'], inplace= True)\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "e541eb18",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.548453Z",
     "iopub.status.idle": "2023-10-05T21:45:43.548831Z",
     "shell.execute_reply": "2023-10-05T21:45:43.548677Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.548661Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "scrolled": true,
    "tags": []
   },
   "outputs": [],
   "source": [
    "df"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "0b4bacef",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### GENERACION DE INSIGHTS"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "b30eead1",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Cuantification del problema: Cual es la tasa de abandono?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "8a656712",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.550500Z",
     "iopub.status.idle": "2023-10-05T21:45:43.550858Z",
     "shell.execute_reply": "2023-10-05T21:45:43.550712Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.550696Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df.abandono.value_counts(normalize = True)* 100"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "4149b76a",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Hay un perfil tipo de empleado que deja la empresa?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "c99e3248",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.554396Z",
     "iopub.status.idle": "2023-10-05T21:45:43.555019Z",
     "shell.execute_reply": "2023-10-05T21:45:43.554764Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.554737Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "#Transformar abondono a numerico\n",
    "df['abandono'] = df['abandono'].replace({'No': 0, 'Yes': 1})\n",
    "\n",
    "# Imprimir el DataFrame\n",
    "df"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "964f6017",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.556838Z",
     "iopub.status.idle": "2023-10-05T21:45:43.557436Z",
     "shell.execute_reply": "2023-10-05T21:45:43.557170Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.557143Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "scrolled": true,
    "tags": []
   },
   "outputs": [],
   "source": [
    "#Analisis por educacion\n",
    "temp = df.groupby('educacion').abandono.mean().sort_values(ascending = False)*1000\n",
    "temp.plot.bar();"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "df0007ec",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.559325Z",
     "iopub.status.idle": "2023-10-05T21:45:43.559878Z",
     "shell.execute_reply": "2023-10-05T21:45:43.559640Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.559614Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "# Analisis por esta do civil"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "f1bd5c4f",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.561940Z",
     "iopub.status.idle": "2023-10-05T21:45:43.562521Z",
     "shell.execute_reply": "2023-10-05T21:45:43.562264Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.562240Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "temp = df.groupby('estado_civil').abandono.mean().sort_values(ascending = False)*1000\n",
    "temp.plot.bar();"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "3423d1fc",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.564367Z",
     "iopub.status.idle": "2023-10-05T21:45:43.564897Z",
     "shell.execute_reply": "2023-10-05T21:45:43.564665Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.564640Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "temp = df.groupby('puesto').abandono.mean().sort_values(ascending = False)*1000\n",
    "temp.plot.bar();"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "a2b325bc",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.567503Z",
     "iopub.status.idle": "2023-10-05T21:45:43.567961Z",
     "shell.execute_reply": "2023-10-05T21:45:43.567799Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.567781Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "temp = df.groupby('abandono').salario_mes.mean()\n",
    "temp.plot.bar();"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "f998c1f5",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### Cloncusiones\n",
    "El perfil medio del empleado que deja la empresa es:\n",
    " * bajo nivel de estudios\n",
    " * soltero\n",
    " * trabaja en ventas\n",
    " * Bajo salario\n",
    "* alta carga de horas extras\n",
    "    "
   ]
  },
  {
   "cell_type": "markdown",
   "id": "0fd01906",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Cual es el impacto economico de este proble,ma?\n",
    "\n",
    "Segun el estudio \"Cot of turnover\"\n",
    "\n",
    "el costo de la fuga de los empleados que ganan menos de 30000 es del 16.1% de su salario.\n",
    "el costo de la fuga de los empleados que ganan entre  30000 y 50000 es del 19.7% de su salario.\n",
    "el costo de la fuga de los empleados que ganan entre  50000 y 75000 es del 20.4% de su salario.\n",
    "el costo de la fuga de los empleados que ganan mas de 75000 es del 21% de su salario."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "f417294f",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.569932Z",
     "iopub.status.idle": "2023-10-05T21:45:43.570382Z",
     "shell.execute_reply": "2023-10-05T21:45:43.570167Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.570149Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "#Creamos una nueva variable salario_ano del empleado\n",
    "df['salario_ano'] =df.salario_mes.transform(lambda x: x*12)\n",
    "df[['salario_mes','salario_ano']]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "d02804a6",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.571844Z",
     "iopub.status.idle": "2023-10-05T21:45:43.572514Z",
     "shell.execute_reply": "2023-10-05T21:45:43.572336Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.572317Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "# Calcular el impacto económico\n",
    "condiciones = [(df['salario_ano'] <= 30000),\n",
    "               (df['salario_ano'] > 30000) & (df['salario_ano']<= 50000),\n",
    "               (df['salario_ano'] > 50000) & (df['salario_ano']<= 75000),\n",
    "               (df['salario_ano'] > 75000)]\n",
    "\n",
    "resultados = [df.salario_ano *0.161, df.salario_ano * 0.197, df.salario_ano * 0.204, df.salario_ano * 0.21]\n",
    "\n",
    "df['impacto_abandono'] = np.select(condiciones,resultados,default= -999)\n",
    "\n",
    "# Imprimir el DataFrame\n",
    "df\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "9e06e08c",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Cuanto nos ha costado este problema el ultimo ano?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "b3f485f0",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.573550Z",
     "iopub.status.idle": "2023-10-05T21:45:43.573886Z",
     "shell.execute_reply": "2023-10-05T21:45:43.573749Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.573734Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "coste_total = df.loc[df.abandono == 1].impacto_abandono.sum()\n",
    "coste_total"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "12aef0c6",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Cuanto nos custa que los empleados no esten motivados? perdidas en implicacion == baja"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "7b962045",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.575066Z",
     "iopub.status.idle": "2023-10-05T21:45:43.575447Z",
     "shell.execute_reply": "2023-10-05T21:45:43.575299Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.575282Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df.loc[(df.abandono == 1)& (df.implicacion == 'Baja')].impacto_abandono.sum()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "8bc18308",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Cuanto dinero podriamos ahorrar fidellizando mejor a nuestro empleados?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "bd2674e6",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.576564Z",
     "iopub.status.idle": "2023-10-05T21:45:43.577275Z",
     "shell.execute_reply": "2023-10-05T21:45:43.577029Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.577005Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "print(f\"Reducir un 10% la fuga de empleados nos ahorraria {int(coste_total *  0.1)} $ cada ano\")\n",
    "print(f\"Reducir un 20% la fuga de empleados nos ahorraria {int(coste_total *  0.2)} $ cada ano\")\n",
    "print(f\"Reducir un 20% la fuga de empleados nos ahorraria {int(coste_total *  0.2)} $ cada ano\")"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "dd4fdd82",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "#### Y podemos seguir tranzando estrategias asociadas a los insights de abondono:\n",
    "\n",
    "Habiamos visto que los reprensantes de ventas son el puesto que mas se va. Tendria sentido hacer un plan especifico para ellos? Cual seria el coste ahorrado si disminuimos la fuga un 30%?\n",
    "Primero vamos a calcular el % de reprensentantes de ventas que se ahan ido el ano pasado."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "36439c0f",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.579270Z",
     "iopub.status.idle": "2023-10-05T21:45:43.579637Z",
     "shell.execute_reply": "2023-10-05T21:45:43.579491Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.579475Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "total_repre_pasado = len(df.loc[df.puesto == 'Sales Representative'])\n",
    "abandonos_repre_pasado = len(df.loc[(df.puesto == 'Sales Representative') & (df.abandono == 1)])\n",
    "porc_pasado = abandonos_repre_pasado / total_repre_pasado\n",
    "\n",
    "porc_pasado"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "f629f071",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Ahora vamos a cuantificar cuantos se nos iran este ano"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "ec52bc76",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.580936Z",
     "iopub.status.idle": "2023-10-05T21:45:43.581357Z",
     "shell.execute_reply": "2023-10-05T21:45:43.581146Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.581130Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "total_repre_actual = len(df.loc[(df.puesto == 'Sales Representative') & (df.abandono == 0)])\n",
    "se_iran = int(total_repre_actual * porc_pasado)\n",
    "se_iran"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "c27e35fb",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Sobre ellos cuantos podemos retener (hipotesis 30%) y cuanto dinero puee suponer"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "fc102992",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.582894Z",
     "iopub.status.idle": "2023-10-05T21:45:43.583294Z",
     "shell.execute_reply": "2023-10-05T21:45:43.583102Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.583086Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "retenemos = int(se_iran * 0.3)\n",
    "ahorramos = df.loc[(df.puesto == 'Sales Representative') & (df.abandono == 0), 'impacto_abandono'].sum()*porc_pasado*0.3\n",
    "print(f'Podemos retener {retenemos} representantes de ventas y ello supondria ahorrar {ahorramos}')"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "ac11e53e",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Este dato tambien es muy interesante porque nos permite determinar el presupuesto para acciones de retencion por departamento o perfil.\n",
    "Ya que sabemos que podemos gastarnos hasta 37.000$ solo en acciones especificas para retener a representantes de ventas y se estarian solo pagando con la perdida evitada."
   ]
  },
  {
   "cell_type": "markdown",
   "id": "af606655",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "## DIA 3 : MODELO DE MACHINE LEARNING"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "c45568bb",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.584883Z",
     "iopub.status.idle": "2023-10-05T21:45:43.585245Z",
     "shell.execute_reply": "2023-10-05T21:45:43.585059Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.585045Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df_ml= df.copy()\n",
    " \n",
    "df_ml.info()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "778b413b",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### PREPARACION DE LOS DATOS PARA LA MODELIZAION"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "bb2add35",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "#### Transformar todas las variables categoricas a numericas"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "851a4476",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.586261Z",
     "iopub.status.idle": "2023-10-05T21:45:43.586605Z",
     "shell.execute_reply": "2023-10-05T21:45:43.586460Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.586444Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "from sklearn.preprocessing import OneHotEncoder\n",
    "\n",
    "#Categoricas\n",
    "cat = df_ml.select_dtypes('O')\n",
    "\n",
    "#Instalaciones\n",
    "\n",
    "ohe = OneHotEncoder(sparse = False)\n",
    "\n",
    "#Entrenamos\n",
    "ohe.fit(cat)\n",
    "\n",
    "#Aplicamos \n",
    "cat_ohe = ohe.transform(cat)\n",
    "\n",
    "#ponemos los nombres\n",
    "cat_ohe = pd.DataFrame(cat_ohe, columns = ohe.get_feature_names_out(input_features = cat.columns)).reset_index(drop = True)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "202da2b1",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.588006Z",
     "iopub.status.idle": "2023-10-05T21:45:43.588435Z",
     "shell.execute_reply": "2023-10-05T21:45:43.588265Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.588231Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "cat_ohe"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "98863adf",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "#### Data Frame Final\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "93fb1693",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Seleccionamos las variables numericas para poder juntarlas a las cat_hoe"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "b24e6336",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.589554Z",
     "iopub.status.idle": "2023-10-05T21:45:43.589906Z",
     "shell.execute_reply": "2023-10-05T21:45:43.589759Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.589743Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "num = df.select_dtypes('number').reset_index(drop= True)\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "09894c14",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Las juntamos todas en el dataframe final"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "a4751141",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.592743Z",
     "iopub.status.idle": "2023-10-05T21:45:43.593116Z",
     "shell.execute_reply": "2023-10-05T21:45:43.592963Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.592947Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df_ml = pd.concat([cat_ohe, num], axis= 1)\n",
    "df_ml"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "15a398c0",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### Diseno de la modelizacion"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "d714eac6",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "#### Separacion predictores y targets\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "8e145ef0",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.596519Z",
     "iopub.status.idle": "2023-10-05T21:45:43.596940Z",
     "shell.execute_reply": "2023-10-05T21:45:43.596779Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.596761Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "x = df_ml.drop(columns= 'abandono')\n",
    "y = df_ml['abandono']"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "8b539afd",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "#### Separacion train y test"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "d21c62d5",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.598069Z",
     "iopub.status.idle": "2023-10-05T21:45:43.598458Z",
     "shell.execute_reply": "2023-10-05T21:45:43.598307Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.598290Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "from sklearn.model_selection import train_test_split\n",
    "train_x, test_x, train_y, test_y = train_test_split(x,y,test_size= 0.3)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "1a77d9d4",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### Entreamiento del modelo sobre train "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "b233711f",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.599884Z",
     "iopub.status.idle": "2023-10-05T21:45:43.600282Z",
     "shell.execute_reply": "2023-10-05T21:45:43.600089Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.600073Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "from sklearn.tree import DecisionTreeClassifier\n",
    "#Instanciar\n",
    "ac = DecisionTreeClassifier(max_depth= 4)\n",
    "#Entrenar\n",
    "ac.fit(train_x,train_y)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "953b27d7",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### Prediccion y validacion sobre test"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "1eaf94e8",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.601770Z",
     "iopub.status.idle": "2023-10-05T21:45:43.602345Z",
     "shell.execute_reply": "2023-10-05T21:45:43.601968Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.601952Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "#Prediccion\n",
    "pred = ac.predict_proba(test_x)[:,1]\n",
    "pred[:20]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "0f20c935",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.604213Z",
     "iopub.status.idle": "2023-10-05T21:45:43.604576Z",
     "shell.execute_reply": "2023-10-05T21:45:43.604429Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.604412Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "#Evaluacion\n",
    "from sklearn.metrics import roc_auc_score\n",
    "\n",
    "roc_auc_score(test_y,pred)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "c323fd0e",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### Interpreatacion"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "ac407d23",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "#### Diagrama de arbol"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "6a101f51",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.605831Z",
     "iopub.status.idle": "2023-10-05T21:45:43.606210Z",
     "shell.execute_reply": "2023-10-05T21:45:43.606030Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.606014Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "from sklearn.tree import plot_tree\n",
    "\n",
    "plt.figure(figsize= (50,50))\n",
    "\n",
    "plot_tree(ac,\n",
    "          feature_names=test_x.columns,\n",
    "          impurity= False,\n",
    "          node_ids= True,\n",
    "          proportion= True,\n",
    "          rounded= True,\n",
    "          precision= 2);"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "038ae413",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.607423Z",
     "iopub.status.idle": "2023-10-05T21:45:43.607742Z",
     "shell.execute_reply": "2023-10-05T21:45:43.607599Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.607584Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "pd.Series(ac.feature_importances_, index = test_x.columns).sort_values(ascending= False).plot(kind= 'bar',figsize= (30,20));"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "7d1723a4",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "###  Explotacion"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "1192b120",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Incorporacion del scoring al dataframe principal."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "64cf9b54",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.609228Z",
     "iopub.status.idle": "2023-10-05T21:45:43.609554Z",
     "shell.execute_reply": "2023-10-05T21:45:43.609414Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.609400Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df['scoring_abandono'] = ac.predict_proba(df_ml.drop(columns = 'abandono'))[:,1]\n",
    "df"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "a36e1e7b",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "Ejemplo de los 10 empleados con mayor probabilidad de dejar la empresa."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "87fa1121",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.611384Z",
     "iopub.status.idle": "2023-10-05T21:45:43.611706Z",
     "shell.execute_reply": "2023-10-05T21:45:43.611565Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.611551Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df.sort_values(by= 'scoring_abandono', ascending= False)[0:10]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "36f68812",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.613004Z",
     "iopub.status.idle": "2023-10-05T21:45:43.613724Z",
     "shell.execute_reply": "2023-10-05T21:45:43.613563Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.613545Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df.boxplot(column= 'scoring_abandono', by ='puesto',figsize = (20,12))"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "c4bf80ca",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "source": [
    "### Guardar el resultado"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "85d0b1cd",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.615435Z",
     "iopub.status.idle": "2023-10-05T21:45:43.616402Z",
     "shell.execute_reply": "2023-10-05T21:45:43.616225Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.616199Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "df"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "6b96c2e7",
   "metadata": {
    "execution": {
     "iopub.status.busy": "2023-10-05T21:45:43.617717Z",
     "iopub.status.idle": "2023-10-05T21:45:43.618060Z",
     "shell.execute_reply": "2023-10-05T21:45:43.617914Z",
     "shell.execute_reply.started": "2023-10-05T21:45:43.617899Z"
    },
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": [
    "# Save the DataFrame to an XLSX file\n",
    "df.to_excel('Employee turnover costs calculation.xlsx')\n",
    "import openpyxl\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "134dfb14",
   "metadata": {
    "papermill": {
     "duration": null,
     "end_time": null,
     "exception": null,
     "start_time": null,
     "status": "pending"
    },
    "tags": []
   },
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.10.12"
  },
  "papermill": {
   "default_parameters": {},
   "duration": 12.851803,
   "end_time": "2023-10-05T21:57:17.310292",
   "environment_variables": {},
   "exception": true,
   "input_path": "__notebook__.ipynb",
   "output_path": "__notebook__.ipynb",
   "parameters": {},
   "start_time": "2023-10-05T21:57:04.458489",
   "version": "2.4.0"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
```

P.S.
------------

Please drop me an note with any feedback you have.

**Roberto Perez**
